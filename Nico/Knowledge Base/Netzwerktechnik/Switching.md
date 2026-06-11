---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
Beim Switching werden Mehrer Geräte an Switche angeschlossen. Diese leiten sogenannte Frames oder Pakete weiter an andere Geräte. Ein Frame hat folgenden Aufbau:  
![[Yxu2qzuKrQ-700.webp]]
Das Switching findet im OSI-Modell auf Schicht zwei statt.
# Vorgehensweise eines Switch
---
Ein Switch hat immer zwei Schritte, die er durchgeht um das Frame oder Paket zum richtigen Ziel weiter zu leiten.
## Schritt 1 - Lernen
Beim Schritt eins wird die Source MAC-Adresse überprüft, ob sie bereits in der MAC-Adressenliste des Switches steht. Wenn die MAC-Adresse noch nicht vorhanden ist, wird die Adresse zusammen mit dem Port in der Liste gespeichert. Ist die Adresse schon vorhanden, so wird geschaut ob der Port noch übereinstimmt und gegebenen Falls angepasst. Zudem wird (wenn Adresse in der Liste vorhanden) der Aktualisierungstimer aktualisiert, da ein Ethernet-Switch alle 5 min einen Eintrag bei nicht aktualisieren löscht.
## Schritt 2 - Forward
Beim Forward schaut sich der Switch erst an, ob die Adresse eine Unicast Adresse ist oder nicht. Wenn sie eine ist überprüft der Switch, ob die Destination MAC-Adresse in der Liste vorhanden ist.

Wenn die Adresse ...
- ... vorhanden ist schickt der Switch die Daten nur an den Gekannten Port.
- ... nicht vorhanden ist werden die Daten an jeden Port, außer an nicht verwendete und den Source-Port geschickt.

Ist der Port ein Broad- oder Multicast, so wird der Frame bzw. das Paket ebenfalls an alle Ports außer an nicht verwendete und den Source-Port weitergeleitet.
# Beispiele
Hier ist ein Beispiel, indem die Ziel-MAC-Adresse nicht bekannt ist.  
![[5-xuaZ0pZ1-700.webp]]

Beim folgendem Beispiel ist die Ziel-MAC-Adresse bekannt.  
![[UM09IMPJIj-700.webp]]