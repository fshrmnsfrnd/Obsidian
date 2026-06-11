---
Fach: "[[BWP]]"
Thema:
  - "[[Wirtschaft und Recht]]"
---
# Betrieblicher Abrechnungsbogen (BAB)

| Kosten in €                   | Gesamt    | Material  | Fertigung | Verwaltung |
| ----------------------------- | --------- | --------- | --------- | ---------- |
| Unprod. Löhne                 | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Ges. soz. Aufwändungen        | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Heizung/Strom                 | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Miete                         | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Werbung                       | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Unprod. kalk. Unternehmerlohn | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Kalk. Abschreibung            | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Kalk. Zinsen                  | `<Wert>`  | `<Wert>`  | `<Wert>`  | `<Wert>`   |
| Summe Gemeinkosten            | `<Summe>` | `<Summe>` | `<Summe>` | `<Summe>`  |
## Kalkulation der Zuschlagsätze

| Art                  | Kosten   |
| -------------------- | -------- |
| Materialeinzelkosten | `<Wert>` |
| Lohneinzelkosten     | `<Wert>` |
| Herstellungskosten   | `<Wert>` |

> [!NOTE] Zuschlagssatz
> $$
> \frac{SummeGemeinkosten * 100}{Einzelkosten}
> $$

| Kosten in €          | Gesamt             | Material             | Fertigung        | Verwaltung               |
| -------------------- | ------------------ | -------------------- | ---------------- | ------------------------ |
| Art der Gemeinkosten | Summe Gemeinkosten | Materialkosten       | Fertigungskosten | Verwaltungskosten        |
| Art der Einzelkosten | Lohneinzelkosten   | Materialeinzelkosten | Lohneinzelkosten | Herstellungseinzelkosten |
| Zuschlagsatz         | `<Wert>%`          | `<Wert>%`            | `<Wert>%`        | `<Wert>%`                |

# Auftrag

| Person                           | Stunden     | Stundenlohn | Gesamt               |
| -------------------------------- | ----------- | ----------- | -------------------- |
| Betriebsinhaber                  | `<Stunden>` | `<Wert>`    | `Stunden * Lohn`     |
| Geselle                          | `<Stunden>` | `<Wert>`    | `Stunden * Lohn`     |
| Lohneinzelkosten                 |             |             | `Summe der Personen` |
| Materialeinzelkosten Auftrag     | `<Wert>`    |             |                      |
| Sondereinzelkosten der Fertigung | `<Wert>`    |             |                      |

# Differenzierte Zuschlagskalkulation
| **Stelle**                            | **Betrag in €** | **Prozent** | Berechnung                |
| ------------------------------------- | --------------- | ----------- | ------------------------- |
| **Materialeinzelkosten**              | **2.000**       |             | `gegeben`                 |
| +Materialgemeinkosten                 | 240             | 12%         | `% aus BAB`               |
| **= Materialkosten**                  | **2.240**       |             | `100% + 12%`              |
| + Fertigungslohnkosten                | 1.100           |             | `Aus Auftrag`             |
| + Fertigungsgemeinkosten              | 176             | 16%         | `% aus BAB`               |
| + Sondereinzelkosten                  | 0               | 0%          | `Aus Auftrag`             |
| **= Herstellkosten**                  | **3.516**       |             | `100% + 1.110 + 16% + 0%` |
| + Verwaltungskosten                   | 914,16          | 26%         | `Aus BAB`                 |
| **= Selbstkosten**                    | **4.430,16**    |             | `100% + 26%`              |
| + Gewinn- und Wagniszuschlag          | 664,52          | 15%         | `gegeben`                 |
| **= Angebotspreis ohne Umsatzsteuer** | **5.094,68**    |             | `100% + 15%`              |
| + Umsatzsteuer                        | 967,99          | 19%         | `Auswendig wissen`        |
| **= Angebotspreis mit Umsatzsteuer**  | **6062,67**     | 119%        | `100% + 19%`              |
# Summarische Zuschlagskalkulation

>Diese Art der Zuschlagskalkulation wird verwendet wenn es wenig Materialkosten gibt. Beispiele sind Unternehmen welche Dienstleistungen anbieten wie z. B. Friseur.

| **Stelle**                            | **Betrag in €** | **Prozent** | Berechnung                |
| ------------------------------------- | --------------- | ----------- | ------------------------- |
| **Materialeinzelkosten**              | **2.000**       |             | `gegeben`                 |
| + Lohneinzelkosten                    | 1.100           |             | `Aus Auftrag`             |
| + Gemeinkosten                        | 670,73          | 61%         | `% aus BAB`               |
| + Sondereinzelkosen                   | 0               | 0%          | `Aus Auftrag`             |
| **= Selbstkosten**                    | **3.770,73**    |             | `100% + 1.100 + 61% + 0%` |
| + Gewinn- und Wagniszuschlag          | 565,61          | 15%         | `Gegeben`                 |
| **= Angebotspreis ohne Umsatzsteuer** | **4.336,34**    |             | `100% + 15%`              |
| + Umsatzsteuer                        | 823,90          | 19%         | `Auswendig wissen`        |
| **= Angebotspreis mit Umsatzsteuer**  | **5.160,25**    | 119%        | `100% + 19%`              |