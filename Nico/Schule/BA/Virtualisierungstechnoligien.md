---
Fach: "[[BA]]"
---
# Virtuelle Maschinen (Hardware Virtualisierung)
---
In jeder dieser Maschinen läuft ein Gastbetriebssystem. Es bekommt isoliert von andern virtuellen Maschinen einen Teil der CPU-Zeit und einen Teil des Arbeitsspeichers zugeteilt. 
## Typ 1
Hypervisor vom Typ 1 laufen direkt auf der Hardware
![[Pasted image 20251216125008.png]]
**Beispiele:**
- Proxmox
- HyperV
- vSphere
- VMware esxi
## Typ 2
 Hypervisor vom Typ 2 laufen als Prozess in einem normalen Betriebssystem.
 ![[Pasted image 20251216125022.png]]
 **Beispiele:**
 - VirtualBox
 - VMWare 
 - Workstation
# Unikernel
---
Ein Unikernel ist eine Anwendung, die gemeinsam mit dem Kernel und den Bibliotheken kompiliert wird. Zu diesem Zweck reduziert man das Betriebssystem auf das, was die Anwendung braucht. Alles andere fällt weg. Ein Unikernel wird in der Regel in einem Hypervisor betrieben.
![[Pasted image 20251216125231.png]]
**Vorteile**
- bessere Performance, vor allem wegen fehlender Kontextwechsel
- hohe Sicherheit durch kleine Angriffsfläche
- Unikernel sind sehr weit voneinander abgekapselt
**Nachteile**
- hoher Aufwand bei Änderungen (Neukompilierungen)
- schwierige Entwicklung

# Container
---
Eine Container-Engine verteilt die Ressourcen eines Betriebssystems auf Container. In jedem dieser Container befindet sich eine Anwendung, die isoliert von anderen Containern auf dem Kernel des Host-Rechners läuft. Die Software Umgebung, die sie über den Kernel hinaus braucht, bringt sie selbst mit.
![[Pasted image 20251216125622.png]]
**Beispiele:**
- Docker
- Podman
- LXC
