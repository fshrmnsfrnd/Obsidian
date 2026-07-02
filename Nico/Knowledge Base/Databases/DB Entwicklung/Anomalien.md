---
Thema:
  - "[[Databases]]"
---
# Änderungs-Anomalie
---
Wenn dieselben Daten an unterschiedlichen Stellen gespeichert werden, müssen die Daten überall Angepasst werden. Tut man das nicht Entsteht [[ANSI-SPARC#Warum Datenbanken?#Redundanzfreiheit|Redundanz]] 
![[Pasted image 20260105174737.png]]
Hier Wurde die Telefonnummer von Hans Schmitz im vorherigem Datensatz übersehen und nicht geändert.
# Einfüg-Anomalie
---
Diese Anomalie entsteht wenn Daten verpflichtend eingegeben werden müssen (hier rot), aber nicht bekannt sind.  
![[Pasted image 20260105174810.png]]
In diesem Beispiel ist es nicht möglich einen Kunden ohne Berater zu erfassen.
# Lösch-Anomalie
---
Wenn man nur ein paar Daten eines Datensatzes (alle Daten einer Zeile) Löschen möchte (hier blau) und auch andere Daten gelöscht werden müssen auf Grund der Datenstruktur und das zu einem Ungewollten Datenverlust führt spricht man von einer Lösch-Anomalie.  
![[Pasted image 20260105174818.png]]
Werden die Datensätze 8 und 9 gelöscht gehen auch die Informationen zum Berater Klaus Maier verloren.  
  
In diesem Beispiel ist die Datenstruktur schlecht, da verschiedene Informationen (Berater und Kunde) in einem Datensatz zusammen gefügt wurden. Dadurch ist die Datenbasis nicht widerspruchsfrei und die Datenbasis ist unzuverlässig