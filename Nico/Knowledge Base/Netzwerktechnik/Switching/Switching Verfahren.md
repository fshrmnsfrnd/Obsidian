---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---

| Switching-Verfahren  | Beschreibung                                                                                                                                                                                                                                                                          | Vorteile                                                                                          | Nachteile                                                                                                                     |
| :------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------- |
| Cut-Through          | Der Switch leitet das Datenpaket **sofort** weiter, wenn er die Adresse des Ziels erhalten hat.                                                                                                                                                                                       | Die **Latenz**, die Verzögerungszeit, zwischen Empfangen und Weiterleiten ist äußerst **gering**. | **Fehlerhafte** Datenpakete werden **nicht erkannt** und trotzdem an den Empfänger weitergeleitet.                            |
| Store-and-Forward    | Der Switch nimmt das gesamte Datenpaket in Empfang und speichert es in einem **Puffer**. Dort wird die **Frame Check Sequence (FCS)** geprüft und bearbeitet. Erst danach wird das Paket an den Ziel-Port weitergeleitet.                                                             | **Fehlerhafte** Datenpakete können so im voraus **aussortiert** werden.                           | Die **Speicherung** und **Prüfung** der Datenpakete verursacht eine **Verzögerung**, abhängig von der Größe des Datenpaketes. |
| Adaptive-Cut-Through | Viele Switches arbeiten mit einer **Kombination** aus Cut-Through und Store-and-Forward. Solange nur **wenige Kollisionen** auftreten wird **Cut-Through** verwendet. **Häufen** sich die Fehler schaltet der Switch auf **Store-and-Forward** um.                                    |                                                                                                   |                                                                                                                               |
| Fragment-Free        | Der Switch empfängt die **ersten 64 Byte** des Daten-Paketes. Ist dieser Teil fehlerlos werden die Daten weitergeleitet. Die **meisten Fehler** und Kollisionen treten während den ersten 64 Byte auf. Dieses Verfahren wird trotz seiner effektiven Arbeitsweise **selten genutzt**. |                                                                                                   |                                                                                                                               |
## Vergleich

| | Store & Forward | Fragement Free | Cut Through |
| - | - | - | -|
| Geschwindingkeite der Datenweiterleitung | normal | schnell | sehr schnell |
|Weiterleitung von Kollisionsfragementen | nein | nein | ja |
|Weiterleitung fehlerhafter Frames (CRC Fehler) | nein | ja | ja |
