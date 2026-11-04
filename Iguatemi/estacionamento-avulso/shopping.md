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

[usb] pm3 --> hf mf auto

[!] ⚠️  Known key failed. Can't authenticate to block   0 key type A
[=] Static Encrypted Nonce Key Recovery
[=] ---------+---------+---------------------------------------------------------+---------------------------+---------------
[=]          |         |                                                         | Expected to verify        | Estimated
[=]  Time    | #nonces | Activity                                                | #keys/candidates          | time for task
[=] ---------+---------+---------------------------------------------------------+---------------------------+---------------
[=]        0 |       0 | Start FM11RF08S static encrypted nonce recovery         |                           |
[=]        0 |       0 | Collect nonce/data evidence with key A396EFA4E24F       |                           |
[=]        1 |      34 | Loaded card UID D2A68703 using backdoor key A396EFA4E24 |                           |
[=]        1 |      34 | Skip default-key dictionary check already done by autop |                           |
[=]        1 |      34 | Generate first-pass candidates from nT/{nT}/parity      |                           |
[=]        3 |      34 | Prepared sec 000 candidates (A 16695 / B 19468)         |                     36163 |
[=]        4 |      34 | Prepared sec 001 candidates (A 12866 / B 11185)         |                     24051 |
[=]        6 |      34 | Prepared sec 002 candidates (A 12849 / B 14282)         |                     27131 |
[=]        8 |      34 | Prepared sec 003 candidates (A 15439 / B 20116)         |                     35555 |
[=]       10 |      34 | Prepared sec 004 candidates (A 18112 / B 18245)         |                     36357 |
[=]       12 |      34 | Prepared sec 005 candidates (A 23004 / B 20751)         |                     43755 |
[=]       14 |      34 | Prepared sec 006 candidates (A 13074 / B 12479)         |                     25553 |
[=]       15 |      34 | Prepared sec 007 candidates (A 7348 / B 7550)           |                     14898 |
[=]       17 |      34 | Prepared sec 008 candidates (A 11968 / B 14149)         |                     26117 |
[=]       18 |      34 | Prepared sec 009 candidates (A 14116 / B 13222)         |                     27338 |
[=]       20 |      34 | Prepared sec 010 candidates (A 14893 / B 13189)         |                     28082 |
[=]       22 |      34 | Prepared sec 011 candidates (A 22285 / B 20182)         |                     42467 |
[=]       24 |      34 | Prepared sec 012 candidates (A 47716 / B 47716)         |                     95432 |
[=]       25 |      34 | Prepared sec 013 candidates (A 11073 / B 12973)         |                     24046 |
[=]       26 |      34 | Prepared sec 014 candidates (A 7479 / B 7322)           |                     14801 |
[=]       27 |      34 | Prepared sec 015 candidates (A 5242 / B 5122)           |                     10364 |
[=]       29 |      34 | Prepared sec 032 candidates (A 10735 / B 9964)          |                     20699 |
[=]       29 |      34 | Prioritized candidates (0 duplicate-priority)           |                    532809 |         30min
[=]       29 |      34 | Indexed 532809 candidate refs for key-reuse cascades    |                    532809 |
[=]       29 |      34 | Refreshed 532809 candidate refs for key-reuse cascades  |                    532809 |
[=]       29 |      34 | Measurement: score unresolved candidate paths           |                    532809 |
[=]       29 |      34 | Measurement: best sec 032 B cost 1 list 9964            |                      9964 |
[=]       29 |      34 | Verify remaining sector-specific candidates             |                    532809 |         30min
[=]       29 |      34 | sec 032 key B - checking 9964 candidates                |                      9964 |           34s
[-]       29 |      34 | sec 032 key B [....................]    102/9964     1% |                      9964 |
[+]       29 |      34 | Key sec 032 key B = 0000F0459AEF                        |                 1/34 keys |
[=]       30 |      34 | Reduced paired candidate sets by 10734 keys             |                     10734 |
[=]       30 |      34 | sec 032 key A - checking 1 candidates                   |                         1 |            1s
[\]       30 |      34 | sec 032 key A [####################]      1/1      100% |                         1 |
[+]       30 |      34 | Key sec 032 key A = C7259BFBC702                        |                 2/34 keys |
[=]       30 |      34 | sec 015 key A - checking 5242 candidates                |                      5242 |           18s
[|]       59 |      34 | sec 015 key A [###################.]   4998/5242    95% |                      5242 |
[+]       59 |      34 | Key sec 015 key A = D278D08EA4F5                        |                 3/34 keys |
[=]       59 |      34 | Reduced paired candidate sets by 5121 keys              |                      5121 |
[=]       59 |      34 | sec 015 key B - checking 1 candidates                   |                         1 |            1s
[|]       59 |      34 | sec 015 key B [####################]      1/1      100% |                         1 |
[+]       59 |      34 | Key sec 015 key B = D872DA84AEFF                        |                 4/34 keys |
[=]       59 |      34 | sec 007 key B - checking 7550 candidates                |                      7550 |           26s
[|]       86 |      34 | sec 007 key B [############........]   4590/7550    60% |                      7550 |
[+]       86 |      34 | Key sec 007 key B = DFD5217FE383                        |                 5/34 keys |
[=]       86 |      34 | Reduced paired candidate sets by 7347 keys              |                      7347 |
[=]       86 |      34 | sec 007 key A - checking 1 candidates                   |                         1 |            1s
[|]       86 |      34 | sec 007 key A [####################]      1/1      100% |                         1 |
[+]       86 |      34 | Key sec 007 key A = E5EF1B45D9B9                        |                 6/34 keys |
[=]       87 |      34 | sec 014 key A - checking 7479 candidates                |                      7479 |           26s
[|]       88 |      34 | sec 014 key A [....................]    306/7479     4% |                      7479 |
[+]       88 |      34 | Key sec 014 key A = 4B526783BBB3                        |                 7/34 keys |
[=]       89 |      34 | Reduced paired candidate sets by 7320 keys              |                      7320 |
[=]       89 |      34 | sec 014 key B - checking 2 candidates                   |                         2 |            1s
[|]       89 |      34 | sec 014 key B [####################]      2/2      100% |                         2 |
[+]       89 |      34 | Key sec 014 key B = 475E6B8FB7BF                        |                 8/34 keys |
[=]       89 |      34 | sec 013 key B - checking 12973 candidates               |                     12973 |           45s
[|]      101 |      34 | sec 013 key B [###.................]   2142/12973   16% |                     12973 |
[+]      101 |      34 | Key sec 013 key B = 4C5411C472EC                        |                 9/34 keys |
[=]      102 |      34 | Reduced paired candidate sets by 11072 keys             |                     11072 |
[=]      102 |      34 | sec 013 key A - checking 1 candidates                   |                         1 |            1s
[|]      102 |      34 | sec 013 key A [####################]      1/1      100% |                         1 |
[+]      102 |      34 | Key sec 013 key A = 4E5613C670EE                        |                10/34 keys |
[=]      102 |      34 | sec 001 key A - checking 12866 candidates               |                     12866 |           44s
[-]      133 |      34 | sec 001 key A [########............]   5508/12866   42% |                     12866 |
[+]      133 |      34 | Key sec 001 key A = 2056F9240481                        |                11/34 keys |
[=]      134 |      34 | Reduced paired candidate sets by 11184 keys             |                     11184 |
[=]      134 |      34 | sec 001 key B - checking 1 candidates                   |                         1 |            1s
[-]      134 |      34 | sec 001 key B [####################]      1/1      100% |                         1 |
[+]      134 |      34 | Key sec 001 key B = 0A7CD30E2EAB                        |                12/34 keys |
[=]      134 |      34 | sec 008 key B - checking 14149 candidates               |                     14149 |           49s
[-]      193 |      34 | sec 008 key B [##############......]  10302/14149   72% |                     14149 |
[+]      193 |      34 | Key sec 008 key B = D1C346100331                        |                13/34 keys |
[=]      193 |      34 | Reduced paired candidate sets by 11967 keys             |                     11967 |
[=]      193 |      34 | sec 008 key A - checking 1 candidates                   |                         1 |            1s
[-]      193 |      34 | sec 008 key A [####################]      1/1      100% |                         1 |
[+]      193 |      34 | Key sec 008 key A = E9FB7E283B09                        |                14/34 keys |
[=]      194 |      34 | sec 003 key B - checking 20116 candidates               |                     20116 |           69s
[/]      297 |      34 | sec 003 key B [#################...]  17952/20116   89% |                     20116 |
[+]      297 |      34 | Key sec 003 key B = 21021ED4811F                        |                15/34 keys |
[=]      298 |      34 | Reduced paired candidate sets by 15437 keys             |                     15437 |
[=]      298 |      34 | sec 003 key A - checking 2 candidates                   |                         2 |            1s
[/]      298 |      34 | sec 003 key A [####################]      2/2      100% |                         2 |
[+]      298 |      34 | Key sec 003 key A = 03203CF6A33D                        |                16/34 keys |
[=]      298 |      34 | sec 002 key B - checking 14282 candidates               |                     14282 |           49s
[\]      376 |      34 | sec 002 key B [##################..]  13566/14282   94% |                     14282 |
[+]      376 |      34 | Key sec 002 key B = 381FCFE0F07A                        |                17/34 keys |
[=]      376 |      34 | Reduced paired candidate sets by 12847 keys             |                     12847 |
[=]      376 |      34 | sec 002 key A - checking 2 candidates                   |                         2 |            1s
[\]      376 |      34 | sec 002 key A [####################]      2/2      100% |                         2 |
[+]      376 |      34 | Key sec 002 key A = 1433E3CCDC56                        |                18/34 keys |
[=]      377 |      34 | sec 010 key A - checking 14893 candidates               |                     14893 |           51s
[|]      440 |      34 | sec 010 key A [##############......]  10914/14893   73% |                     14893 |
[+]      440 |      34 | Key sec 010 key A = 5BF0A0DFCEAE                        |                19/34 keys |
[=]      440 |      34 | Reduced paired candidate sets by 13188 keys             |                     13188 |
[=]      440 |      34 | sec 010 key B - checking 1 candidates                   |                         1 |            1s
[|]      440 |      34 | sec 010 key B [####################]      1/1      100% |                         1 |
[+]      440 |      34 | Key sec 010 key B = 67CC9CE3F292                        |                20/34 keys |
[=]      440 |      34 | sec 006 key A - checking 13074 candidates               |                     13074 |           45s
[-]      447 |      34 | sec 006 key A [#...................]   1122/13074    8% |                     13074 |
[+]      447 |      34 | Key sec 006 key A = E8D8E3BFB246                        |                21/34 keys |
[=]      447 |      34 | Reduced paired candidate sets by 12477 keys             |                     12477 |
[=]      447 |      34 | sec 006 key B - checking 2 candidates                   |                         2 |            1s
[-]      447 |      34 | sec 006 key B [####################]      2/2      100% |                         2 |
[+]      447 |      34 | Key sec 006 key B = D4E4DF838E7A                        |                22/34 keys |
[=]      448 |      34 | sec 009 key A - checking 14116 candidates               |                     14116 |           49s
[\]      523 |      34 | sec 009 key A [##################..]  13158/14116   93% |                     14116 |
[+]      523 |      34 | Key sec 009 key A = 5A2F95388CB7                        |                23/34 keys |
[=]      523 |      34 | Reduced paired candidate sets by 13220 keys             |                     13220 |
[=]      523 |      34 | sec 009 key B - checking 2 candidates                   |                         2 |            1s
[\]      524 |      34 | sec 009 key B [####################]      2/2      100% |                         2 |
[+]      524 |      34 | Key sec 009 key B = 6015AF02B68D                        |                24/34 keys |
[=]      524 |      34 | sec 000 key B - checking 19468 candidates               |                     19468 |           67s
[\]      525 |      34 | sec 000 key B [....................]    204/19468    1% |                     19468 |
[+]      525 |      34 | Key sec 000 key B = C5D6E2F272DA                        |                25/34 keys |
[=]      525 |      34 | Reduced paired candidate sets by 16692 keys             |                     16692 |
[=]      525 |      34 | sec 000 key A - checking 3 candidates                   |                         3 |            1s
[\]      526 |      34 | sec 000 key A [####################]      3/3      100% |                         3 |
[+]      526 |      34 | Key sec 000 key A = EDFECADA5AF2                        |                26/34 keys |
[=]      526 |      34 | sec 011 key A - checking 22285 candidates               |                     22285 |           76s
[\]      539 |      34 | sec 011 key A [##..................]   2346/22285   10% |                     22285 |
[+]      539 |      34 | Key sec 011 key A = 3BCCC3913B05                        |                27/34 keys |
[=]      540 |      34 | Reduced paired candidate sets by 20180 keys             |                     20180 |
[=]      540 |      34 | sec 011 key B - checking 2 candidates                   |                         2 |            1s
[\]      540 |      34 | sec 011 key B [####################]      2/2      100% |                         2 |
[+]      540 |      34 | Key sec 011 key B = 39CEC1933907                        |                28/34 keys |
[=]      540 |      34 | sec 005 key A - checking 23004 candidates               |                     23004 |           79s
[\]      648 |      34 | sec 005 key A [################....]  18768/23004   81% |                     23004 |
[+]      648 |      34 | Key sec 005 key A = E12ED1CAE01F                        |                29/34 keys |
[=]      649 |      34 | Reduced paired candidate sets by 20750 keys             |                     20750 |
[=]      649 |      34 | sec 005 key B - checking 1 candidates                   |                         1 |            1s
[\]      649 |      34 | sec 005 key B [####################]      1/1      100% |                         1 |
[+]      649 |      34 | Key sec 005 key B = C30CF3E8C23D                        |                30/34 keys |
[=]      649 |      34 | sec 004 key B - checking 18245 candidates               |                     18245 |           63s
[\]      721 |      34 | sec 004 key B [#############.......]  12444/18245   68% |                     18245 |
[+]      721 |      34 | Key sec 004 key B = 891F64826D5F                        |                31/34 keys |
[=]      721 |      34 | Reduced paired candidate sets by 18111 keys             |                     18111 |
[=]      721 |      34 | sec 004 key A - checking 1 candidates                   |                         1 |            1s
[\]      721 |      34 | sec 004 key A [####################]      1/1      100% |                         1 |
[+]      721 |      34 | Key sec 004 key A = A93F44A24D7F                        |                32/34 keys |
[=]      722 |      34 | sec 012 key A - checking 47716 candidates               |                     47716 |          2min
