---
Fach: "[[DB]]"
tags:
Thema:
  - "[[MySQL]]"
---
| MySQL-Datentyp                    | Bedeutung                                                                                                                           |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| ``TINYINT(m)``                    | 8-Bit-Ganzzahl (-128 bis +127); die optionale Angabe m gibt die gewünschte Spaltenbreite bei der Ausgabe von SELECT-Ergebnissen an. |
| ``SMALLINT(m)``                   | 16-Bit-Ganzzahl (-32768 bis +32767)                                                                                                 |
| ``MEDIUMINT(m)``                  | 24-Bit-Ganzzahl (-8388608 bis +8388607)                                                                                             |
| ``INT(m),INTGER(m)``              | 32-Bit-Ganzzahl (-2147483648 bis +2147483647)                                                                                       |
| ``BIGINT(m)``                     | 64-Bit-Ganzzahl (+9,22*1018 )                                                                                                       |
| ``SERIAL``                        | Gleiche Bedeutung wie BIGINT AUTO_INCREMENT NOT NULL PRIMARY KEY                                                                    |
| ``FLOAT(m,d)``                    | 4-Byte-Fließkommazahl; m ist die Anzahl von Stellen insgesamt und d die Anzahl von Stellen nach dem Dezimalpunkt.                   |
| ``DOUBLE(m,d)``                   | 8-Byte-Fließkommazahl                                                                                                               |
| ``REAL(m,d)``                     |                                                                                                                                     |
| ``DECIMAL(p,s) NUMERIC(p,s) DEC`` | Festkommazahl; p gibt die gesamte Stellenanzahl an, s gibt die Anzahl der Nachkommastellen an.                                      |
| ``DATE``                          | Datum im Format jjjj-mm-tt z.B. 2008-11-20                                                                                          |
| ``TIME``                          | Zeit im Format hh:mm:ss z.B. 22:11:27                                                                                               |
| ``DATETIME``                      | Kombination aus DATE und TIME z.B. 2008-11-20 22:11:27                                                                              |
| ``YEAR``                          | Jahreszahl im Bereich 1900-2155                                                                                                     |
| ``TIMESTAMP``                     | Datum und Zeit im Format von DATETIME. Diese Zeitangabe wird von MySQL automatisch bei jeder Änderung aktualisiert.                 |
| ``CHAR(n)``                       | Zeichenkette mit vorgegebener Länge n; maximaler Wert für n: 255                                                                    |
| ``VARCHAR(n)``                    | Zeichenkette mit variabler Länge.Es sind maximal n Zeichen möglich.                                                                 |
| ``TINYTEXT``                      | Zeichenkette mit variabler Länge bis zu 255 Zeichen                                                                                 |
| ``TEXT``                          | Zeichenkette mit variabler Länge bis zu 216-1 Zeichen                                                                               |
| ``MEDIUMTEXT``                    | Zeichenkette mit variabler Länge bis zu 224-1 Zeichen                                                                               |
| ``LONGTEXT``                      | Zeichenkette mit variabler Länge bis zu 232-1 Zeichen                                                                               |
