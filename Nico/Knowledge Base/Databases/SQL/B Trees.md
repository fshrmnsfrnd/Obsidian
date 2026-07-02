---
Thema:
  - "[[Databases]]"
---
>Um große Mengen von Daten geordnet zu organisieren, werden Baumstrukturen verwendet. In der Datenbankwelt wird der sogenannte B-Tree häufig verwendet. Beim B-Tree ist jeder Knoten eine ganze Page

![[Pasted image 20260102141334.png]]
@https://sven.ziegler.page/#/page/b-tree
# Daten einfügen
---
**Regeln**
- Zuerst wird der Knoten gesucht, in den das neue Element gehört. 
- Wenn der Knoten noch Platz für das neues Element hat, wird es dort eingefügt.
- Ist kein Platz mehr, wird der Knoten beim mittleren Element (Median) in zwei neue Knoten zerlegt. Das Median-Element wird in den übergeordneten Knoten eingefügt. Die beiden neuen Knoten sind jetzt exakt halb voll. 
- Sollte der übergeordnete Knoten aufgrund des zusätzlichen Median-Elements ebenfalls seine Kapazität überschreiten, wird auch dieser Knoten zerlegt. Sein Median-Element rutscht eine Ebene nach oben – und so weiter …
![[Pasted image 20260102134232.png]]

# Daten löschen
---
Soll ein Element gelöscht werden, werden folgende Fälle unterschieden
## Leaf löschen
- Zunächst wird das Element wird entfernt 
- Ist der Knoten nach der Entfernung weniger als 50 % befüllt, wird der Baum neu ausbalanciert.
![[Pasted image 20260102134441.png]]
## Knoten löschen
- Zunächst wird das Element entfernt. 
- Das neue Trenn-Element wird entweder das letzte Element des linken Subknotens, oder das erste Element des rechten Subknotens. In der Regel wird das Element aus dem Knoten genommen, der mehr Elemente enthält. 
- Das ausgewählte Element des Subknotens wird in die Lücke eingebaut.
- Wenn durch das Verschieben des Elements der betroffene Subknoten weniger als halb voll ist, wir der Baum neu ausbalanciert.

![[Pasted image 20260102134457.png]]
# Ausbalancieren
---
**Regeln**
- Beginne immer bei einem Blatt-Knoten der weniger als m/2 Elemente enthält. 
- Gibt es in einem Nachbarknoten (Sibling) mit genügend Elementen, verschieben Sie ein Element davon in den übergeordneten Knoten und das bisherige Trennelement in den zu kleinen Subknoten. Dieser Vorgang heißt Rotation. 
- Wenn keine Rotation in Frage kommt, weil es keinen geeigneten Nachbarknoten gibt, werden zwei benachbarte Knoten zu einem zusammengefügt. Das nennt man Merge. Bei einem Merge wird dem übergeordneten Knoten ein Element entnommen und in den Sub-Knoten verschoben. 
- Hat durch einen Merge der übergeordnete Knoten zu wenig Elemente, muss dort das Ausbalancieren fortgesetzt werden. Es werden die gleichen Regeln angewendet.

![[Pasted image 20260102134608.png]]
# Varianten
---
### B+ Tree 
Beim B+-Tree enthalten nur die Endknoten (*Blätter*) Key-Value-Einträge, wobei als Schlüssel die zu indizierenden Werte dienen, als Werte die Querverweise auf Pages der Datenbank. 
Die Knoten in den übergeordneten Ebenen enthalten dagegen nur Keys sowie Verweise auf andere Knoten. Außerdem sind die Knoten einer Ebene durch direkte Links (ähnlich einer Linked List) miteinander verbunden. 
B+ Trees werden im MS SQL Server, Oracle und in SQLite eingesetzt. Sie werden auch in NoSQL-Datenbank Systemen verwendet. z.B. CouchDB. 

### B* Tree 
Beim B* Tree müssen Knoten zu mindestens 2/3 gefüllt werden. Knoten, die voll sind, werden nicht sofort in zwei neue Teilknoten getrennt; stattdessen wird versucht, Elemente in Nachbarknoten zu verschieben. Diese beiden Maßnahmen führen dazu, dass Knoten im Schnitt dichter befüllt sind und weniger häufig in zwei neue Knoten zerlegt werden müssen. 

Weiter Alternativen sind Präfix Trees und Hash-Tree.
# Nice to Know
---
- Die *Ordnungszahl* gibt an wie viele `Subknoten` ein `Knoten` hat