---
Thema:
  - "[[Java]]"
---
# native Datentypen
---

| Name    | Beschreibung                                                                                                                                              |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| byte    | The byte data type is an 8-bit signed two's complement integer. It has a minimum value of -128 and a maximum value of 127 (inclusive).                    |
| short   | The short data type is a 16-bit signed two's complement integer. It has a minimum value of - 32,768 and a maximum value of 32,767 (inclusive).            |
| int     | By default, the int data type is a 32-bit signed two's complement integer, which has a minimum value of -231 and a maximum value of 231-1.                |
| long    | The long data type is a 64-bit two's complement integer. The signed long has a minimum value of $-2^{63}$ and a maximum value of $2^{63 -1}$ .            |
| float   | The float data type is a single-precision 32-bit IEEE 754 floating point.                                                                                 |
| double  | The double data type is a double-precision 64-bit IEEE 754 floating point.                                                                                |
| boolean | The Boolean data type has only two possible values: true and false.                                                                                       |
| char    | The char data type is a single 16-bit Unicode character. It has a minimum value of '\u0000' (or 0) and a maximum value of '\uffff' (or 65,535 inclusive). |
# Variablentypen
---
>Variablen sind innerhalb geschweifter Klammern "{}" gültig. Bei gleichem Namen können sie sich  nicht überdecken.
## final
`final int x;`
- Attribut kann **nur einmal** gesetzt werden.
- Danach unveränderlich.
- Bei `static final`: echte Konstante.
## public
`public int a;`
- Von überall zugreifbar.
- Klassen, Pakete, Vererbung: egal.
- Wird sparsam verwendet, meist für APIs oder Konstanten.
## private
`private int b;` 
- Nur innerhalb **derselben Klasse** sichtbar.
- Standard für Attribute.
- Zugriff von außen nur über Getter/Setter.
## protected
`protected int c;`
- Sichtbar:
    - innerhalb derselben Klasse
    - innerhalb desselben Pakets
    - in **Unterklassen** (auch in anderen Paketen)
- Wird bei Vererbung genutzt.
## static
`public static int d;`
- Gehört **zur Klasse**, nicht zum Objekt.
- Es gibt **nur eine** gemeinsame Variable für alle Instanzen.
- Zugriff über `Klassenname.attribut`.

