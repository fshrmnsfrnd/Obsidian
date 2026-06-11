---
Fach: "[[Berufsschule]]"
---
>Virtualisierung erlaubt es Physische Hardware / Ressourcen logisch aufzuteilen oder zusammenzufassen. Für diesen Vorgang wird ein Hypervisor benötigt.
# Nested Virtualisation
---
Wenn man eine Virtuelle Maschine in einer anderen VM macht, nennt man das **Nested Virtualisation**.
# Was wird Virtualisiert?
---

| Hardware              |
| --------------------- |
| [[CPU]]                   |
| Systeme bzw. Hardware |
| Betriebssysteme       |
| Anwendungen           |
| Desktop               |
| Rechenzentren         |
| [[RAM]]                   |
| [[Festplatten]]           |
| Storage               |
| Netzwerk              |

# Vorteile und Nachteile
---

|**Vorteile**|**Nachteile**|
|---|---|
|bessere Hardware Ausnutzung|weniger Perfomance|
|leichtere Bereitstellung (z. B. von Servern)|nicht jede Hardware kann Virtualisiert werden|
|mehr Flexibilität(kopieren von VMs)|kann Single Point of Failure sein|
|leichtere Software-Tests und Entwicklung für verschiedene Systeme|komplex|
# Arten
---
Es gibt verschiedene Arten der Virtualisierung mit verschiedenen Eigenschaften.

Oft spielt bei der Virtualisierung der Hypervisor eine wichtige Rolle. Er ist eine Software, die es ermöglicht [[Betriebssystem]] zu virtualisieren.
## Level 1 Virtualisierung
>Bei der Level 1 Virtualisierung wird der sogenannte Hypervisor auf den Ring 0 geschoben.

Dadurch entsteht eine sehr schnelle Verbindung zwischen Hardware und Betriebssystem.  
  ![[is5Mw5bbqT-544.webp]]
Ein solcher Hypervisor ist z. B. HyperV.

## Level 2 Virtualisierung
>Bei der Level 2 Virtualisierung befindet sich der Hypervisor über dem Host-OS. Es ist weniger Performant als eine Level 1 Virtualisierung, jedoch besser für Testumgebungen geeignet.  

Programm-Beispiele sind:
- Virtual Box
- KVM
- VMware  

![[DJfOhWXwPO-521.webp]]
## Emulation Virtualisierung
>Bei der Emulation wird nicht nur die Hardware geteilt bzw. zusammen gefügt sondern es wird nicht vorhandene Hardware simuliert. Das benötigt man um z. B. alte Programme auf neuer Hardware laufen zu lassen. Oder um Software auf andere CPU-Archetektur zu testen. (z. B. ARM auf einem x64 System) 

![[GZHYOctWee-524.webp]]
## Application Virtualisierung
Wenn nur einzelne APPs in einer VM laufen, nennt man das **Applikations-Virtualisierung**. Ein Beispiel dafür ist JAVA mit dem **J**ava **V**irtual **M**aschine (**JVM**).  

![[fFTd2OqbeB-571.webp]]
## Betriebssystem Virtualisierung
Bei einer Betriebssystem-Virtualisierung wird der Kernel des Vorhandenen Host-OS verwendet und lediglich ein weiterer User-Mode hinzugefügt.  
Programm-Beispiele sind [[Knowledge Base/Tools/Docker]]-Container.  

![[0tEz40S7CV-636.webp]]