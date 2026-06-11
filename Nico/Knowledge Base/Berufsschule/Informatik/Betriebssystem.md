---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Operating System]]"
---
Das Betriebssystem ist das bindeglied zwischen Hardware und Software. Oft wird eine **Summe** von **Betriebssystemkern (Kernel)** und **wichtige Systemprogrammen** als Betriebssystem verstanden. Zudem stellt ein Betriebssystem **Schnittstellen (APIs)** zwischen Software und Hardware bereit. Die wichtigste Aufgabe eines Betriebssystems ist die **Resourcenverwaltung**.

![[w7Yq5eoZU2-700.webp]]
# Aufgaben eines Betriebssystems
---

![[hwKNrYG1Gs-700.webp]]
## Prozessverwaltung
Damit mehrere Benutzer gleichzeitig und/oder ein Benutzer gleichzeitig mehrere Aktionen durchführen kann ohne sich in die Quere zu kommen müssen diese **Prozesse** verwaltet werden. Ein Prozess ist z. B. ein gestartetes Programm.
## Speicherverwaltung
**Zuteilen** von **Speicherbereichen** an laufende Prozesse, **Schutz** der **Speicherbereiche** vor unbefugten Zugriffen, bei Speicherengpässen: **Auslagern** (swapping) von ganzen oder von Teilen (paging) von Prozessen auf die Platte in Dateien ([[swap]] file, page file) oder Partitionen ([[swap]] partition)
## Dateiverwaltung
Zuteilung von **Plattenplatz** für Programme, Benutzer und Systemdienste, **Schreiben**, **Lesen** und **Strukturieren** der **Daten** auf Massenspeichern. Dafür Stellt der Kernel eine API für die Entsprechenden **Dateisysteme** zur Verfügung.

## Geräteverwaltung
Der **kontrollierte** Zugriff auf **Hardware** wie z. B. Eingabe- und Ausgabe Geräte der Anwender wird mittels **Gerätetreiber** ermöglicht.
# Eigenschaften von Betriebssystemen
---
## Multitasking
Beim **Multitasking** werden **NICHT** mehrere Programme gleichzeitig ausgeführt, sondern den Programmen werden lediglich Zeit Slots (**Zeitscheiben**) zu gewiesen in denen sie Arbeiten dürfen. Dies wird von einem **Schedular** verwaltet.  
![[2ezU3kAiqc-700.webp]]

## Mehrprozessorbetrieb
Moderne Betriebssysteme unterstützten mehrere Prozessorkerne auf einmal. Dadurch können in jedem Kerne jeweils **EINE** aufgabe **pro Kern gleichzeitig** durchgeführt werden.
## Multi-Threading
Um ein Programm n och schneller laufen zu lassen besteht die möglichkeit des **Multi-Threadings**. Dabei werden Programm-Schnipsel **Threads** auf verschiedene Kerne **gleichzeitig** aufgeteilt. Dies muss aber von dem **Betriebssystem**, dem **Programm**, und der **Hardware** unterstützt sein.
# CPU-Ringe
---
Ein Betriebssystem wird gerne in Ringen Dargestellt.  
  ![[CEdEpQFXpN-700.webp]]
**Kernel-Mode** oder auch **Ring 0** ist der Teil, der mit der Hardware direkt Kommuniziert. Er stellt APIs bereit, wodurch der User über den **Ring 3** (**User-Mode**) auf die Hardware zugreifen kann.