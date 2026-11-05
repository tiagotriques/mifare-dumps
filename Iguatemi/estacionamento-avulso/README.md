```
[usb] pm3 --> hf mf info

[=] --- ISO14443-a Information -----------------------------
[+]  UID: D2 A6 87 03
[+] ATQA: 00 04
[+]  SAK: 08 [2]

[=] --- Keys Information
[+] loaded 2 user keys
[+] loaded 64 hardcoded keys
[+] Backdoor key..... A396EFA4E24F
[+] Block 0.......... D2A68703F0080400052CB45E0DD2D790 | .,.^....

[=] --- Fingerprint
[+] Fudan FM11RF08S 0590

[=] --- Magic Tag Information
[=] <n/a>

[=] --- PRNG Information
[+] Prng....... weak
[+] Static enc nonce... yes
[?] Hint: Try `hf mf sen`
```

![](./estacionamento-avulso-front.jpg)

![](./estacionamento-avulso-back.jpg)

Obrigado pelo backdoor :P


# Clanker section

# MIFARE Classic Parking Ticket Analysis

Card UID: `D2 A6 87 03`  
Dump format: MIFARE Classic 1K, 1024 bytes = 64 blocks × 16 bytes  

Date of ticket: **2026-11-03**  
Entry: **15:11**  
Paid until: **19:11**

## Summary

| Finding | Location |
|---|---|
| Parking-system card number | Block 1, bytes 0–1; repeated in block 4, bytes 4–5 |
| Entry timestamp | Sector 1, block 4, bytes 8–11 (`0x048–0x04B`) |
| Paid duration | Sector 1, block 4, bytes 12–14 (`0x04C–0x04E`) |
| Payment/status field | Sector 1, block 5, bytes 2–3 (`0x052–0x053`) |
| Sector checksums | Last byte of blocks 6, 10, and 14 |

The paid-until time is **not stored as an absolute timestamp**. It is derived from:

```text
entry timestamp + paid duration
```

## Parking-System Card Number

The parking system assigns its own card number, independent of the MIFARE UID.

For this card the number is **37956**, which is `0x9444`, stored little-endian:

```text
37956 decimal = 0x9444 -> bytes 44 94
```

It appears in two places:

```text
block 1, bytes 0–1 (offset 0x010): 44 94
block 4, bytes 4–5 (offset 0x044): 44 94
```

## Block 4 — Entry Time and Paid Duration

Block 4 is at dump offset `0x040` (sector 1, first data block).

```text
Dump-002 (before):
72 00 45 01 | 44 94 10 81 | 92 F9 E9 6A | FF FF 3F 00

Dump-003 (after):
72 00 45 01 | 44 94 10 81 | 92 F9 E9 6A | 40 38 00 00
```

| Block byte(s) | Dump-002 | Dump-003 | Meaning |
|---|---|---|---|
| 0 | `72` | `72` | Record type/version |
| 1–3 | `00 45 01` | `00 45 01` | Fixed header/application marker |
| 4–5 | `44 94` | `44 94` | Parking-system card number `0x9444` = 37956, little-endian |
| 6–7 | `10 81` | `10 81` | Facility/issuer code |
| 8–11 | `92 F9 E9 6A` | `92 F9 E9 6A` | Entry timestamp, 32-bit little-endian |
| 12–14 | `FF FF 3F` | `40 38 00` | Duration in seconds, 24-bit little-endian |
| 15 | `00` | `00` | Reserved/padding |

### Entry timestamp

`92 F9 E9 6A` read little-endian:

```text
0x6AE9F992 = 1,793,718,674
= 2026-11-03 15:11:14
```

### Paid duration

Before payment:

```text
FF FF 3F 00 -> 0x003FFFFF = 4,194,303 seconds
```

This is a sentinel/default value, not a real duration.

After payment:

```text
40 38 00 00 -> 0x00003840 = 14,400 seconds = 4 hours
```

Calculation:

```text
15:11:14 + 4 hours = 19:11:14
```

The other after-payment sample shows the same layout:

```text
3A 39 00 00 -> 0x0000393A = 14,650 seconds = 4h 04m 10s
```

## Blocks 6, 10, 14 — Sector Checksums

The last byte of blocks 6, 10, and 14 is a simple 8-bit additive checksum/LRC.

```text
block 6:   1F 55  ->  2F 76
block 10:  1F 9F  ->  2F 8F
block 14:  1F E2  ->  2F D2
```

Correction: these are **blocks 6, 10, and 14**. Block 15 is the sector-3 trailer, so its final bytes are KeyB, not a checksum.

Only the final byte is the checksum. The second-to-last byte (`1F` -> `2F`) is a data/status flag.

Checksum rule:

```text
checksum = (-sum(sector data bytes except checksum byte)) & 0xFF
```

Equivalent: all 48 data bytes of the sector sum to `0 mod 256`.

```text
block 6  checksum = -(sum(blocks 4,5,6[0:15]))  & 0xFF
block 10 checksum = -(sum(blocks 8,9,10[0:15])) & 0xFF
block 14 checksum = -(sum(blocks 12,13,14[0:15])) & 0xFF
```

---

## Practical Conclusion

To read the parking timing information:

1. Go to **block 4** (`0x040`).
2. Read bytes **8–11** as a 32-bit little-endian timestamp.
3. Read bytes **12–14** as a 24-bit little-endian duration in seconds.
4. Compute:

```text
paid-until = entry timestamp + duration
```

For this ticket:

```text
entry      = 2026-11-03 15:11:14
duration   = 14,400 s = 4 h
paid-until = 2026-11-03 19:11:14
```

Block 5 records the payment amount and validation status:

```text
bytes 0–1: uint16 LE amount (D2 after: 1200 = 12.00)
byte 2:    payment/tariff/terminal code
byte 3:    status (0x38 = unpaid, 0x58 = paid)
```

Blocks 6, 10, and 14 carry sector checksums in their final byte.

Valeu opencode :)
