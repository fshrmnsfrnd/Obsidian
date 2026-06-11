---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
>Auch Stibitz Code genannt

# Excess 3 Tetraden bilden

Dezimalzahl normal zu Binär, und dann + 3 (0011)
## Beispiel
32 = 0011 0010
0011 0010 + 0011 0011 = 0110 0101

# Zehnerkomplement bilden
1. alle Bits flippen
2. zur rechtesten Tetrade 1 addieren
![[Excess 3 Code 18-01-25 14.26.07.excalidraw]]

# Addition
1. [[#Excess 3 Tetraden bilden]]
2. Addieren
3. Wenn aus der höchsten Tetrade ein Übertrag entsteht, wird links eine neue Tetrade hinzugefügt
5. Wenn aus einer Tetrade ein Übertrag entsteht, 0011 zur Tetrade addieren
6. Wenn aus einer Tetrade kein Übertrag entsteht, 1101 ([[#Zehnerkomplement]] von 0011) zur Tetrade addieren.

> [!NOTE] Überträge bei Korrektur
> Wenn bei einer Korrekturaddition (Schritt 4 oder 5) ein Übertrag in die nächste Tetrade entsteht, wird dieser verworfen

6. von jeder Tetrade 3 (0011) abziehen
7. Aus den Tetraden wieder Dezimalziffern bilden

### Beispiel
![[Excess 3 Code 18-01-25 14.11.07.excalidraw]]


# Subtraktion
1. Vom Subtrahenden das [[#Zehnerkomplement bilden]]
2. Die [[#Addition]] durchführen

> [!NOTE] Übertrag wird zu Vorzeichen
> Bei der Subtraktion wird links keine Tetrade hinzugefügt, sondern vom Übertrag das Vorzeichen des wahren Ergebnisses abgelesen (0 = - / 1 = +) 

3. vom Ergebnis das [[#Zehnerkomplement bilden]]
4. von jeder Tetrade 3 (0011) abziehen
5. Aus den Tetraden wieder Dezimalzahlen bilden

# Gegenüberstellung von [[Excess 3 Code]] vs. [[BCD Code]]

## Vorteile: (Excess-3)

- Gute technische Umsetzbarkeit in Mikrokontrollern wegen der einfachen Berechnung NK und ZK im Vergleich BCD-Code, wegen Symmetrie.
- Dadurch dass 0000 in den Bereich der Pseudotetraden fällt, können Systemausfälle leicht erkannt werden.
- Einfach zu Schematisieren

## Nachteile:

- Die Konvertierung in das Binärsystem ist schwieriger, da Bitstellen keinem Stellenwert zugeordnet sind.
- Das manuelle Rechnen ist komplizierter