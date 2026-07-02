---
Thema:
  - "[[MySQL]]"
---
# Nummerische Funktionen
---

| Funktion | Beschreibung |
| --- | --- |
| `ABS(Zahl)` | Der Absolutwert einer Zahl wird ermittelt |
| `ACOS(Cosinuswert)` | Der Arcuscosinus von Cosinus-Wert wird ermittelt. |
| `ASIN(Sinuswert)` | Der Arcussinus von Sinuswert wird ermittelt. |
| `ATAN(Tangenswert)` | Der Arcustangens von Tangens-Wert wird ermittelt. |
| `BIN(Dezimalzahl)` | Eine Dezimalzahl wird in eine Binärzahl umgewandelt |
| `BIT_COUNT(Dezimalzahl)` | Die Anzahl der Einsen wird ermittelt, die die Dualzahl enthält, die der Dezimalzahl entspricht. |
| `CEILING(Zahl)` | Die kleinste Zahl wird ermittelt, die nicht kleiner ist als das Argument. |
| `CONV(Zahl, Basis1, Basis2)` | Das Argument Zahl wird aus dem Zahlensystem mit der Basis1 in das Zahlensystem mit der Basis2 konvertiert. |
| `COS(Bogenmaß)` | Der Cosinus von Bogenmaß wird ermittelt. |
| `COT(Bogenmaß)` | Der Kotangens von Bogenmaß wird ermittelt. |
| `DEGREES(Bogenmaß)` | Das Bogenmaß wird in das entsprechende Gradmaß konvertiert. |
| `EXP(Exponent)` | Die natürliche Basis e wird mit Exponent potenziert. |
| `FLOOR(Zahl)` | Die größte Ganzzahl wird ermittelt, die nicht größer ist als der Argumentwert. |
| `FORMAT(Zahl, Dezimalstellen)` | Eine Zahl wird mit der vorgegebenen Anzahl der Dezimalstellen dargestellt. |
| `GREATEST(Zahl1, Zahl2,...)` | Die größte Zahl der Liste wird ermittelt.|
| `HEX(Dezimalzahl)`                     | Eine Dezimalzahl wird in die entsprechende Hexadezimalzahl konvertiert.                          |
| `LEAST(Zahl1, Zahl2, ...)`            | Die kleinste Zahl der Liste wird ermittelt.                                                      |
| `LN(Zahl)`                             | Der natürliche Logarithmus einer Zahl wird ermittelt.                                            |
| `LOG(Zahl)`                            | Gleiche Wirkung wie `LN(Zahl)`.                                                                  |
| `LOG2(Zahl)`                           | Der Logarithmus der Zahl zur Basis 2 wird ermittelt.                                             |
| `LOG10(Zahl)`                          | Der Logarithmus der Zahl zur Basis 10 wird ermittelt.                                            |
| `MOD(Dividend, Divisor)`              | Der Rest einer Ganzzahlteilung wird ermittelt.                                                   |
| `OCT(Dezimalzahl)`                     | Eine Dezimalzahl wird in die entsprechende Oktalzahl umgewandelt.                                |
| `PI()`                                 | Der Wert π wird geliefert.                                                                       |
| `POW(Basis, Exponent)`                | Die Potenz Basis hoch Exponent wird ermittelt.                                                   |
| `POWER(Basis, Exponent)`              | Gleiche Wirkung wie `POW(Basis, Exponent)`.                                                      |
| `RADIANS(Grad)`                        | Das Gradmaß wird in das entsprechende Bogenmaß umgewandelt.                                      |
| `RAND()`                               | Eine Zufallszahl zwischen 0 und 1 wird ermittelt.                                                |
| `ROUND(Zahl, Nachkommastellen)`       | Rundet eine Zahl auf die angegebenen Nachkommastellen.                                           |
| `SIGN(Zahl)`                           | Liefert -1 bei negativer Zahl, 0 bei Zahl = 0, 1 bei positiver Zahl.                             |
| `SQRT(Zahl)`                           | Die Quadratwurzel einer Zahl wird ermittelt.                                                     |
| `SIN(Bogenmaß)`                        | Der Sinus von Bogenmaß wird ermittelt.                                                           |
| `TAN(Bogenmaß)`                        | Der Tangens von Bogenmaß wird ermittelt.                                                         |
| `TRUNCATE(Zahl, Dezimalstellen)`      | Es werden Dezimalstellen abgeschnitten. Das zweite Argument legt fest, wie viele erhalten bleiben. |
# Datum 
---
## Funktionen
| Funktion                               | Beschreibung                                                                                                  |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `DATE_ADD(Datum, INTERVAL value unit)` | Das Datum wird ermittelt, das sich aus der Addition eines gegebenen Datums und einem Zeitintervall ergibt.    |
| `DATE_SUB(Datum, INTERVAL value unit)` | Das Datum wird ermittelt, das sich aus der Subtraktion eines Zeitintervalls von einem gegebenen Datum ergibt. |
| `DATEDIFF(Datum1, Datum2)`             | Ermittelt die Differenz zwischen Datum1 und Datum2 in Tagen.                                                  |
| `DATE_FORMAT(Datum, Format)`           | Ein Datum wird formatiert.                                                                                    |
| `DAYNAME(Datum)`                       | Der Name des Wochentages bei gegebenem Datum wird ermittelt.                                                  |
| `DAYOFMONTH(Datum)`                    | Aus einem Datum wird der Tag des Monats als numerischer Wert ermittelt.                                       |
| `NOW()`                                | Das aktuelle Datum und die aktuelle Zeit werden ermittelt.                                                    |
| `MONTH(Datum)`                         | Der Monat eines Datums wird als numerischer Wert ermittelt.                                                   |
| `QUARTER(Datum)`                       | Das Quartal eines Datums wird als numerischer Wert ermittelt.                                                 |
| `WEEK(Datum)`                          | Die Woche eines Datums wird als numerischer Wert ermittelt.                                                   |
| `YEAR(Datum)`                          | Das Jahr eines Datums wird ermittelt.                                                                         |
| `TO_DAYS(Datum)`                       | Die Tagesdifferenz zwischen einem Datum und dem 01.01.0001 wird ermittelt.                                    |
|                                        |                                                                                                               |
Alter berechnen:
`TRUNCATE(DATEDIFF(CURDATE(),Geburtsdatum)/365.25, 0) as 'Alter'`

## Einheiten
| Unit         | Beschreibung        |
| ------------ | ------------------- |
| `SECOND`     | Sekunde             |
| `MINUTE`     | Minute              |
| `HOUR`       | Stunde              |
| `DAY`        | Tage                |
| `MONTH`      | Monate              |
| `QUARTER`    | Quartal             |
| `YEAR`       | Jahre               |
| `YEAR_MONTH` | Jahre und Monate    |

## Formatcodes
| Formatcode | Beschreibung                                                                 |
|------------|-------------------------------------------------------------------------------|
| `%a`       | Der abgekürzte Wochentag-Name wird erzeugt (z. B. Mon, Tue, ...).            |
| `%b`       | Der abgekürzte Monatsname wird erzeugt (z. B. Sep, Oct, ...).                |
| `%d`       | Der Tag des Monats wird als numerischer Wert erzeugt.                        |
| `%D`       | Der Tag des Monats wird in der Form 1st, 2nd, ... erzeugt.                   |
| `%m`       | Die Monatsnummer (bezogen auf den Jahresbeginn) wird erzeugt.                |
| `%M`       | Der vollständige Name des Monats wird erzeugt.                               |
| `%w`       | Der Wochentag wird als numerischer Wert erzeugt (0 = Sonntag, 6 = Samstag).  |
| `%W`       | Der vollständige Wochentag-Name wird erzeugt.                                |
| `%y`       | Die Jahreszahl wird im Format „jj“ erzeugt (z. B. 08).                        |
| `%Y`       | Die Jahreszahl wird im Format „jjjj“ erzeugt (z. B. 2008).                   |

# Zeit
---
## Funktionen
| Funktion                                         | Beschreibung                                                                                         |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------|
| `CURTIME()`                                      | Die aktuelle Zeit wird geliefert.                                                                    |
| `DATE_ADD(Datum-Zeit, INTERVAL value unit)`     | Durch Addition eines Zeitintervalls wird ein neuer Zeitwert berechnet.                              |
| `DATE_SUB(Datum-Zeit, INTERVAL value unit)`     | Durch Subtraktion eines Zeitintervalls wird ein neuer Zeitwert berechnet.                           |
| `DATE_FORMAT(Datum-Zeit, Format)`               | Die Ausgabe von Datums- und Zeitwerten wird formatiert.                                              |
| `HOUR(Datum-Zeit)`                              | Aus einer Zeit- oder kombinierten Zeit/Datumsangabe wird die Stundenangabe extrahiert.              |
| `MINUTE(Datum-Zeit)`                            | Aus einer Zeit- oder kombinierten Zeit/Datumsangabe wird die Minutenangabe extrahiert.              |
| `NOW()`                                          | Die aktuelle Zeit wird in Kombination mit dem aktuellen Datum geliefert.                            |
| `SECOND(Datum-Zeit)`                            | Aus einer Zeit- oder kombinierten Zeit/Datumsangabe wird die Sekundenangabe extrahiert.             |
| `TIME_FORMAT(Zeit)`                             | Die Ausgabe von Zeitwerten wird formatiert.                                                          |
| `TIME_TO_SEC(Zeit)`                             | Ein Zeitwert wird in Sekunden umgerechnet.                                                           |

## Formatcodes
| Formatcode | Beschreibung                                                                 |
|------------|------------------------------------------------------------------------------|
| `%H`       | Die Stundenzahl einer Zeitangabe wird dargestellt (zweistellig, 00–23).     |
| `%i`       | Die Minutenzahl einer Zeitangabe wird dargestellt.                          |
| `%S`       | Die Sekundenzahl wird immer zweistellig dargestellt (z. B. 05, 09, 42).      |
| `%s`       | Die Sekundenzahl wird ein- oder zweistellig dargestellt (z. B. 5, 42).       |
| `%T`       | Die vollständige Zeitangabe im 24-Stunden-Format wird dargestellt (HH:MM:SS).|
| `%p`       | Der AM/PM-Zusatz wird dargestellt.                                           |

# String Funktionen
---

| Funktion                                                     | Beschreibung                                                                           |
| ------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| `AES_ENCRYPT(Zeichenfolge, Passwort)`                        | Wie `DECODE`, aber sicherer.                                                           |
| `AES_DECRYPT(Binärzeichenfolge, Passwort)`                   | Wie `ENCODE`, aber sicherer.                                                           |
| `ASCII(Zeichenfolge)`                                        | Es wird der ASCII-Wert des ersten Zeichens einer Zeichenfolge ermittelt.               |
| `CONCAT(Zeichenfolge1, Zeichenfolge2, ...)`                  | Mehrere Zeichenfolgen werden zu einer Zeichenfolge verknüpft.                          |
| `CONCAT_WS(Trennzeichen, Zeichenfolge1, Zeichenfolge2, ...)` | Wie `CONCAT`, allerdings können beliebige Trennzeichen verwendet werden.               |
| `DECODE(Zeichenfolge, Passwort)`                             | Eine Zeichenfolge wird verschlüsselt.                                                  |
| `ENCODE(Binärzeichenfolge, Passwort)`                        | Eine Binärzeichenfolge wird entschlüsselt.                                             |
| `INSTR(Zeichenfolge1, Zeichenfolge2)`                        | Es wird die Position von `Zeichenfolge2` innerhalb von `Zeichenfolge1` ermittelt.      |
| `LCASE(Zeichenfolge)`                                        | Die Buchstaben einer Zeichenfolge werden in Kleinbuchstaben verwandelt.                |
| `LEFT(Zeichenfolge, Zeichenzahl)`                            | Der linke Teil einer Zeichenfolge wird geliefert. Die Länge entspricht `Zeichenzahl`.  |
| `LOCATE(Zeichenfolge1, Zeichenfolge2)`                       | Es wird die Position von `Zeichenfolge1` innerhalb von `Zeichenfolge2` ermittelt.      |
| `RIGHT(Zeichenfolge, Zeichenzahl)`                           | Der rechte Teil einer Zeichenfolge wird geliefert. Die Länge entspricht `Zeichenzahl`. |
| `TRIM(Zeichenfolge)`                                         | Führende und folgende Leerzeichen einer Zeichenkette werden entfernt.                  |
| `UCASE(Zeichenfolge)`                                        | Die Buchstaben einer Zeichenfolge werden in Großbuchstaben verwandelt.                 |
