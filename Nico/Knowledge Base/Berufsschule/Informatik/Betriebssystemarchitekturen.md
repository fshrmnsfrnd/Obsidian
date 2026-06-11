---
Thema:
  - "[[Operating System]]"
---
Zusammenfassung — [[Betriebssystemarchitekturen]]

# Kernfunktionen des Kernels
Der Kernel (Betriebssystemkern) ist die Schnittstelle zwischen Hardware und Anwenderprogrammen. Er sorgt für:
- Bereitstellung hardwareunabhängiger Dienste für Programme (Systemaufrufe),
- Ressourcenverwaltung (z. B. CPU-Scheduling),
- Konfliktauflösung beim Gerätezugriff,
- Überwachung von Zugriffsrechten (Dateien, Speicher).

Der Windows-Kernel liegt z. B. in C:\Windows\System32\ntoskrnl.exe.

> [!IMPORTANT] Der Kernel läuft im privilegierten Modus (Ring 0) und hat volle Rechte. Anwenderprogramme laufen im Benutzermodus (Ring 3).
# Zugriffsschutz / CPU-Ringe
![[Pasted image 20260312164628.png]]
Kurz: x86-CPUs bieten vier Ringe, moderne OS nutzen meist nur Ring 0 (Kernel) und Ring 3 (User).  
Systemaufrufe übergeben kurz die Kontrolle an den Kernel — dieser Kontextwechsel kostet Zeit.
# Kernel-Varianten
![[Pasted image 20260312164744.png]]
- Monolithischer Kernel: Viele Dienste laufen im Kernelmodus (z. B. traditionelles Linux; oft modular erweiterbar).  
- Microkernel: Nur Grundfunktionen im Kernel, viele Dienste in Usermodus (mehr Kontextwechsel).  
- Hybridkernel: Mischung aus beiden (z. B. Windows, macOS).
# Speicherzuweisung
![[Pasted image 20260312165013.png|194]]
Programme bekommen logische Adressräume. Typische Segmentaufteilung:
- Programm-Segment (statisch),
- Daten-/Heap-Segment (wächst nach oben, dynamischer Speicher),
- Stack-Segment (wächst nach unten, lokale Variablen, Rücksprungadressen).
Prozesskontrollblock enthält benötigte Verwaltungsinformationen. Für dauerhaft benötigte Daten: Heap statt Stack.
# Physische vs. logische Adressen
![[Pasted image 20260312165251.png]]
Programme arbeiten mit logischen Adressen (Adressraum beginnt bei 0). Die MMU (Memory Management Unit) übersetzt logische in physische Adressen und ermöglicht Isolation mehrerer Prozesse im physischen RAM.
> Hinweis: Die MMU macht virtuelle Speicherverwaltung und schützt Prozesse, indem sie individuelle logische Adressräume abbildet.
# Speicherschutz (Basis/Grenze)
![[Pasted image 20260312165353.png]]
- Basisregister: enthält die niedrigste physische Adresse des Prozesses.  
- Grenzregister: enthält Größe des erlaubten Adressraums.  
Damit verhindert das System, dass ein Prozess außerhalb seines Bereichs liest oder schreibt.
Kurz: MMU + Basis-/Grenzregister gewährleisten, dass Prozesse nur erlaubten Speicher nutzen.