---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
# Endian
Zur Erkennung wird die Byte Order Magnitude (BOM) verwendet.

**Little Endian BOM:** FFFE
**Big Endian BOM:** FFFF

# BMP
Der Codepoint ist zwischen 0000$_{16}$ und FFFF$_{16}$
# Innerhalb des BMPs 
wird der Codepoint 1:1 übersetzt

z.B. 
U+0062 (b) = UTF16BE 0062

# Außerhalb der BMPs
1. Codepoint in Binär umrechnen
2. 65536$_{10}$ bzw. 0001 0000 0000 0000 0000$_2$ abziehen
3. in 2 Zehn Bit Zahlen aufteilen
4. erste Hälfte D800$_{16}$ bzw. 1101 1000 00$_2$ addieren
5. zweite Hälfte DC00$_{16}$ bzw. 11 0111 0000$_2$ addieren
6. Die Hälften wieder zusammenfügen und in Hex umwandeln