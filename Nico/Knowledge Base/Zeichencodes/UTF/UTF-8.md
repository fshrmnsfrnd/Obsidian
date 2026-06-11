---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
# Umrechnung Unicode UTF-8

| Unicode Codepoint    | Gesetzte Unicode Bits | UTF-8 Bytes | UTF-8 Byte 1 | UTF-8 Byte 2 | UTF-8 Byte 3 | UTF-8 Byte 4 |
| -------------------- | --------------------- | ----------- | ------------ | ------------ | ------------ | ------------ |
| U+0000 bis U+007F    | 7                     | 1           | 0xxx xxxx    | /            | /            | /            |
| U+0080 bis U+07FF    | 11                    | 2           | 110x xxxx    | 10xx xxxx    | /            | /            |
| U+0800 bis<br>U+FFFF | 16                    | 3           | 1110 xxxx    | 10xx xxxx    | 10xx xxxx    | /            |
| U+10000 bis U+10FFFF | 21                    | 4           | 1111 0xxx    | 10xx xxxx    | 10xx xxxx    | 10xx xxxx    |
>Der erste Bereich ist gleich mit ASCII-Code

## Beispiel
![[Pasted image 20241227141055.png]]
