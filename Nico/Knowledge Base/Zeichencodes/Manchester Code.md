---
Fach:
Thema:
  - "[[Zeichencodes]]"
---
Zur Anpassung von Datensignalen an die Eigenschaften physischer Übertragungsleitungen werden verschiedene Kodierungen eingesetzt. Hier werden lediglich einige exemplarisch dargestellt. 

Der Zweck von Kodierungen ist u.a.: 
- Fehlererkennung (z.B. durch Redundanz, CRC) 
- Taktsynchronisation von Sender und Empfänger
- Erzeugung von Gleichstromfreiheit 
- Bandbreitenreduktion durch Kodierung mehrerer Bits pro Symbol 

Der Manchestercode zeichnet sich nach IEEE 802.3 durch folgende Definition aus: - eine fallende Flanke eine logische 0 eine steigende Flanke eine logische 1 (es existiert auch eine Definition bei der die steigende Flanke ein logische 0 bedeutet)

![[Manchester Code 02-10-25 14.54.34.excalidraw]]
Ein Empfänger kann das Taktsignal aus dem Code ableiten, da pro Datenbit ein Flankenwechsel existiert. Damit bestehen zwei Leitungsbits pro Datenbit, wodurch eine gleichstromfreie Übertragung mit dem Einsatz von Impulstransformatoren zur galvanischen Trennung ermöglicht wird. Die Manchesterkodierung "wurde" beim 10-MBit/s Ethernet eingesetzt (10Base5 und 10Base2). 
Da für jedes Datenbit zwei Leitungsbits verwendet werden, damit 2 Symbole, wird für eine Datenübertragung mit 10-MBit/s eine Baudrate von 20-MBit/s erforderlich, womit hier die erforderlich Bandbreite um den Faktor 2 erhöht wird.