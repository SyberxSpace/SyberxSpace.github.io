---
title: Reverse Engineering the PWP Format
date: 2020-12-12 19:00:00 -0500
categories: [Random]
tags: [retro, code, typewriter]
---

I created this document while working with my Smith Corona PWP 78 DS, a 'Personal Word Processor' typewriter capable of reading and writing files to a floppy drive. It uses a proprietary *.pwp* format to encode files so I wanted to understand it so I could create new documents with an external computer. This is what I was able to discover.

![PWP 78 DS](/assets/img/resources/posts/pwp_78_ds.jpg){: width="500"}

---

## Header Format

```
?? ?? 20 20:20 20 20 20|20 20 20 20:20 4D 4C 34
44 20 27 39:32 01 00 FP|SP PS MT MB:ML ML MR MR
66 00 1A 01:00 00 00 00|00 00 00 00:00 00 00 00
00 00 00 00:00 00 00 00|00 00 00 00:00 00 00 00
```

| Code | Meaning | Values | Default |
|------|---------|--------|---------|
| `??` | Size of file | *16-bit unsigned* | |
| `FP` <br><br> | Pitch <br><br> | `06` = 10 <br>  `05` = 12 <br> `04` = 15 | `06` <br><br> |
| `SP` <br><br> | Spacing <br><br> | `02` = single <br>  `03` = 1.5 <br> `04` = double | `02` <br><br> |
| `PS` <br><br><br> | Paper length <br><br><br> | `42` = 11" <br>  `46` = A4 <br> `54` = 14" <br> `FC` = No limit | `42` <br><br><br> |
| `MT` | Top margin | | `06` |
| `MB` | Bottom margin | | `06` |
| `ML` | Left margin | *16-bit unsigned* | `48 00` |
| `MR` <br> | Right margin <br> | *16-bit unsigned* <br> Limit is `52 02` | `B0 01` <br> |

**Rows 3-4 are tabs in 2 byte sets**

First two bits of second byte are tab type:

| `00` | Normal tab |
| `11` | Decimal tab |
| `10` | Tab center |
| `01` | Flush right |

Default tabs are `66 00` and `1A 01`. All positions seem to be multiples of 6.

---

## Special Characters

| `10` | New Line |
| `13` | Superscript |
| `14` | Subscript |
| `20` | Space |
| `0E` | New Page |

## Special Formatting

| Bold | `01` [A] `01` [B] `01` [C] |
| Underline | `02` [A] `02` [B] `02` [C] |
| Bold Underline | `03` [A] `03` [B] `03` [C] |
| Tab | `07 1E 1E 1E 1E 1E` [ABC]  |
| Center | `08 1E 1E .. .. 1E` [ABC] `0D` |

---

## Supported Characters

| `21` | ! |
| `22` | " |
| `23` | # |
| `24` | $ |
| `25` | % |
| `26` | & |
| `27` | ' |
| `28` | ( |
| `29` | ) |
| `2A` | * |
| `2B` | + |
| `2C` | , |
| `2D` | - |
| `2E` | . |
| `2F` | / |
| `30` <br> &nbsp; ↕ <br> `39` | 0 <br> ↕ <br> 9 |
| `3A` | : |
| `3B` | ; |
| `3D` | = |
| `3F` | ? |
| `40` | @ |
| `41` <br> &nbsp; ↕ <br> `5A` | A <br> ↕ <br> Z |
| `5B` | [ |
| `5D` | ] |
| `5E` | ^ &nbsp; &nbsp; &nbsp; *- Connects to next character* |
| `5F` | _ |
| `60` | ` &nbsp; &nbsp; &nbsp; *- Connects to next character* |
| `61` <br> &nbsp; ↕ <br> `7A` | a <br> ↕ <br> z |
| `7E` | ~ &nbsp; &nbsp; &nbsp; *- Connects to next character* |
| `82` | é |
| `87` | ç |
| `A8` | ¿ |
| `AB` | ½ |
| `AC` | ¼ |
| `BD` | ¢ |
| `F4` | ¶ |
| `F5` | § |
