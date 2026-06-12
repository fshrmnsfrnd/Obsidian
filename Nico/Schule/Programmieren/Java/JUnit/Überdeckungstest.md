---
Thema:
  - "[[Programmieren]]"
  - "[[Tests]]"
Fach: "[[Programmieren]]"
---
>Kontrollfluss orientierte Tests sind gängige White Box Verfahren
# C0 – Anweisungsüberdeckung
---
> [!abstract] Statement Coverage Mindestens **einmalige Ausführung jeder Anweisung** (Knoten) des Prüflings.

**Ziel**
- Jede ausführbare Anweisung mind. einmal durchlaufen
- Sicherstellen, dass kein _toter Code_ existiert
**Eigenschaften**
- Notwendiges, aber **nicht hinreichendes** Kriterium
- Als eigenständiges Verfahren ungeeignet
- Bestandteil höherwertiger Verfahren (z.B. Zweigüberdeckung)
**Metrik**
$$\text{C0} = \frac{\text{ausgeführte Anweisungen}}{\text{alle Anweisungen}}$$
# C1 – Zweigüberdeckung
---
> [!abstract] Branch Coverage Ausführung **aller Zweige** (Kanten) des Prüflings.

**Ziel**
- Jeder Zweig mind. einmal durchlaufen
- Nachweis, dass keine nie ausgeführten Zweige existieren
**Eigenschaften**
- Enthält die Anweisungsüberdeckung (C0) vollständig
**Schwächen**
- _Kombinationen_ von Zweigen und komplexe Bedingungen werden nicht berücksichtigt
- Schleifen werden nicht ausreichend getestet (ein einzelner Durchlauf genügt)
- Fehlende Zweige sind nicht direkt entdeckbar
**Metrik**

$$\text{C1} = \frac{\text{ausgeführte Zweige}}{\text{alle Zweige}}$$
# C3 – Bedingungsüberdeckung
---
> [!info] Abgrenzung Betrachtet **atomare Bedingungen** innerhalb von Entscheidungen (`&&`, `||`, `XOR`). Bei rein atomaren Entscheidungen fällt C3 praktisch mit C1 zusammen.
## C3a – Einfachbedingungsüberdeckung
> [!note] Prinzip Jede **atomare** Bedingung wird mind. einmal mit `true` **und** `false` belegt.

**Eigenschaften**
- Einfachster aller C3-Tests
- Deckt Fehler aus dem Zusammenwirken mehrerer atomarer Bedingungen auf
> [!warning] Schwäche Es ist **nicht** sichergestellt, dass die _Gesamtbedingung_ sowohl `true` als auch `false` wird.
## C3b – Mehrfachbedingungsüberdeckung
> [!note] Prinzip **Alle möglichen Kombinationen** der atomaren Bedingungen werden getestet.

**Eigenschaften**
- Anzahl der Kombinationen: $2^n$ ($n$ = Anzahl atomarer Bedingungen)
- Sehr hoher Aufwand durch **exponentiellen** Anstieg
> [!warning] Schwäche In der Praxis wegen Laufzeit und Aufwand oft **nicht durchführbar**.
## C3c – Minimale Mehrfachbedingungsüberdeckung
> [!note] Prinzip Jede **atomare** Bedingung **und** die **Gesamtbedingung** werden auf `true` und `false` gesetzt.

**Eigenschaften**
- Kompromiss zwischen C3a (findet zu wenig) und C3b (dauert zu lang)
- Enthält **C0**, **C1** und **C3a** vollständig
# Überblick
---

|Verfahren|Kriterium|Aufwand|Enthält|
|---|---|---|---|
|**C0**|jede Anweisung ausgeführt|gering|–|
|**C1**|jeder Zweig ausgeführt|gering–mittel|C0|
|**C3a**|jede atomare Bedingung `true`/`false`|mittel|C0, C1|
|**C3b**|alle Kombinationen ($2^n$)|sehr hoch|C0, C1, C3a|
|**C3c**|atomare Bed. + Gesamtbed. `true`/`false`|mittel–hoch|C0, C1, C3a|
