---
Fach:
Thema:
  - "[[Networks]]"
---
>**T**ransport **C**ontrol **P**rotocol Layer 4
# Was ist TCP
---
Bei der Datenübertragung in IP Netzen, werden Daten beim Versenden in Pakete verteilt und beim Empfang wieder zusammengesetzt.
Für die kontrollierte Übertragung wird TCP eingesetzt
- Anwendungen werden entlastet
- Die Netzlast erhöht sich
# UDP Verbindungen
---
- Anwendungen übernehmen die Flusskontrolle
- geringere Netzlast aber erhöhte Rechenlast bei Sender und Empfänger


| 7 Byte   | 1 Byte | 6 Byte   | 6 Byte    | 4 Byte   | 2 Byte | max 1500 Byte            | 4 Byte |
| -------- | ------ | -------- | --------- | -------- | ------ | ------------------------ | ------ |
| Präambel | SFD    | Ziel MAC | Quell MAC | [[VLAN]] | Typ    | Maximum Transer Unit MTU | FCS    |
# TCP Segment
---
![[Pasted image 20260423135418.png]]

| Field                  | Length (bit) | Description                                                                                                                |
| ---------------------- | ------------ | -------------------------------------------------------------------------------------------------------------------------- |
| Source Port            | 16           | Port beim Absender                                                                                                         |
| Destination Port       | 16           | Port beim Empfänger                                                                                                        |
| Sequence Number        | 32           | Offset der Daten im Segment zu den gesamten Daten.                                                                         |
| Acknowledgement Number | 32           | empfangene Sequence Number + Länge des Segments + 1                                                                        |
| Offset                 | 4            |                                                                                                                            |
| Reserved               | 4            |                                                                                                                            |
| Flags                  | 4            | URG (Urgent) \| ACK (Acknowledge) \| PSH (Push Flag) \| RST (Reset Flag) \| SYN (Synchronize) \| FIN (Ende der Verbindung) |
| Window                 | 16           | Buffersize des Empfängers (Es darf nichts größeres gesendet werden)                                                        |
| Checksum               | 16           | Basicly Hash des gesamten Segments                                                                                         |
| Urgent Pointer         | 16           | Nur gültig wenn URG Flag gesetzt ist. Pointer auf Daten die sofort verarbeitet werden müssen                               |
| Options                | 24           | Maximum Segment Size                                                                                                       |
| Padding                | 8            | So lang, dass die Länge des Headers ein Vielfaches von 32 ist                                                              |
# TCP Ablauf
---
## Three Way Handshake
![[TCP 2026-04-23 14.37.04.excalidraw]]
## Datenaustausch ohne Windowing
![[TCP 2026-04-23 14.49.58.excalidraw]]
Hier wird jedes Segment ein ACK gesendet, daher wenig Performanz. Daher:
## Datenaustausch mit Windowing
![[TCP 2026-04-23 15.03.46.excalidraw]]