---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[C++]]"
---
# C-Datentypen mit vorgegebener Breite

| Muster für den Datentyp    | Bedeutung                                                                                                                                                       |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| intN_t uintN_t             | Ein int-Wert mit einer Breite von exakt N Bits. Dieser Typ ist optional und wird nicht vom aktuellen Standard gefordert. Beispiel: uint8_t hat genau 8 Bit.     |
| int_leastN_t uint_leastN_t | Ein int-Wert mit einer Breite von mindestens N Bits. Beispiel: uint_least16_t hat mindestens 16 Bit.                                                            |
| int_fastN_t uint_fastN_t   | Der schnellste int-Typ mit mindestens einer Breite von N Bits. Beispiel: int_fast32_t ist der schnellste Ganzzahltyp mit Vorzeichen, der mindestens 32 Bit hat. |
| intmax_t uintmax_t         | Größtmöglicher ganzzahliger Typ.                                                                                                                                |
# Minimal und Maximalwerte

## header
`#include <climits>`

## Beispiele
`INT_MAX, INT_MIN, UINT_MAX (für unsigned int), INT16_MAX (für int16_t)`

