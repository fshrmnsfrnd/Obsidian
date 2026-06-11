---
tags:
Fach:
Thema:
  - "[[Elektrotechnik]]"
---
![[Leitungsverhalten bei Hochfrequenten Signalen 23-09-25 14.36.37.excalidraw]]

# Experimente
---
## Experiment 1: 
>Spannungsmessung des Generatorausgangs bei ein und ausgesteckter Leitung

**$U_{ein} = U_{aus}$**
das heißt, die Leerlaufspannung ($U_{aus}$) ist doppelt so groß, wie $U_{ein}$ , die Spannung mit verbundener Leitung. 

**Begründung:** Leistungsanpassung bei Belastung durch die Leitung (Hier weil $Z_w = R_i$) 

## Experiment 2: 
>Die Leitung bleibt nun am Generator angeschlossen, der Abschlusswiderstand wird entfernt und wieder angeschlossen.

**Wir beobachten:** die Spannung am Generator bleibt exakt gleich (**konstant**) 
Auch bei Verlängerung der Leitung bleibt die Klemmspannung am Generator konstant.

> [!NOTE] Aus den Experimenten folgt:
> Die Leitung stellt die Last dar, nicht der Abschlusswiderstand (Hochfrequenzbetrachtung)

# Schematische Darstellung der Anzeige des Oszilloskops
---

![[Leitungsverhalten bei Hochfrequenten Signalen 25-09-25 11.59.02.excalidraw]]
Signallaufzeit ist die Ausbreitungsgeschwindigkeit des Signals. Hier bei einer Leitungslänge von 100m. 
$$
c = \frac{l}{t} = \frac{100m}{0.5\micro s} \approx 2 * 10^8 \frac{m}{s}
$$

> [!NOTE] Vergleich Lichtgeschwindigkeit im Vakuum
> $$
> C_o \approx 3*10^8 \frac{m}{s}
> $$

# Verkürzungsfaktor
---
$$
k = \frac{C}{C_o}
$$
# NVP (engl. nominal velocity of propagation)
---
$$NVP=K*100=\frac{C}{C_o}*100\% $$ 
Typische Werte für Netzwerkleitungen: 60% - 80%

# Untersuchung der Signalreflexion bei Leerlauf und Kurzschluss der Leitung
---
![[Pasted image 20251123001815.png]]

Der Abschlusswiderstand ist entfernt worden. Das Signal wird am Leitungsende reflektiert. Da die eingespeiste Energie in der Leitungskapazität gespeichert und wieder abgegeben wird. Am Leitungsende addieren sich Generatorimpuls und Reflexionsimpuls, weil sie gleichphasig sind.
> [!Warning]  doppelte Spannung am Leitungsende
# Kurzschluss am Leitungsende
---
![[Leitungsverhalten bei Hochfrequenten Signalen 25-09-25 12.55.08.excalidraw]]

Durch den Kurzschluss wird die Leitungskapazität wirkungslos
- Strom im Leiter baut ein Magnetfeld auf, in dem die Impulsenergie gespeichert wird
- Am Impulsende bricht das Magnetfeld ein
=> es wird eine gegenpolige Spannung induziert, um den Strom weiter aufrecht zu erhalten

Bei Abschluss der Leitung mit $R_{ab} =$ Wellenwiderstand wird die eingespeiste Energie in $R_{ab}$ in Wärme umgesetzt => <span style="color: green;">KEINE REFLEXION</span>

# Wellenwiderstand in Hochfrequenzbetrachtung
---
$$Z_w=\frac{L'}{C'}​​$$
## Dämpfung und Dämpfungsmaß
---
![[Der Wellenwiderstand in der Hochfequenzbetrachtung 30-09-25 14.04.03.excalidraw]]
### Leitungsdämpfung
$$a_p = 10 log(\frac{P_{ein}}{P_{aus}}) dB$$mit 
$$P = \frac{U^2}{R}$$
### Spannungsdämpfung
$$
a_U = 20*log(\frac{U_{ein}}{U_{aus}}) dB
$$
**Beispiele**

| Faktor     | 1   | $\sqrt{2}$ | 2   | 10  | 20  | 100 | 1000 |
| ---------- | --- | ---------- | --- | --- | --- | --- | ---- |
| $a_p / dB$ | 0   | 1,5        | 3   | 10  | 13  | 20  | 30   |
| $a_U / dB$ | 0   | 3          | 6   | 20  | 26  | 40  | 60   |
