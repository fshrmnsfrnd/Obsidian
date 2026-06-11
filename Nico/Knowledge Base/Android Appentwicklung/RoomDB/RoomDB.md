---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>RoomDB ist eine Bibliothek die es ermöglicht Apps leicht um eine Datenbank zu erweitern. RoomDB verwendet als Datenbank **SQLite**

# Architektur
---
![[Pasted image 20260222130142.png]]
Danke an https://sven.ziegler.page/#/page/roomdb für die Zeichnung
![[Pasted image 20260222124804.png]]
## User Interface
Hier werden alle [[Views]] für die Interaktion bereitgestellt. Sie dient als **Benutzerschnittstelle**.
## UI-Controller
Diese Schicht dient als Schnittstelle zwischen **User Interface** und den **Schichten darunter**. Es gibt die **Eingaben weiter** an die unteren Schichten weiter und **aktualisiert die UI** wenn sich was in der Datenbank ändert.
## ViewModel
Hier wir die Trennung von **UI** und **Datenmodel mit seiner Logik** umgesetzt. Das ViewModel kennt keine Bestandteile des UI-Controller. Wenn der UI-Controller Daten benötigt werden sie von dieser Schicht geholt.  
Das ViewModel-Objekt bleibt im Speicher auch wenn der UI-Controller im Rahmen neu erstellt wird.
## Repository
Das Repository verwaltet Daten aus **externen Datenquellen** wie z. B. **Datenbanken** oder **Web-Services**. Diese Klasse verwaltet die Kommunikation zu den verschiedenen Quellen.
## LiveData, Observer, View
**LiveData-Objekte** ermöglichen es innerhalb des **ViewModels** werte zu **beobachten** (**Observer**). Diese beobachtbaren Objekte können andere Objekte über Änderungen **informieren**. Dadurch kann die **UI** sich immer aktualisieren wenn die Daten im **ViewModel** sich ändern.
# RoomDB Bibliothek
---
![[Pasted image 20260222125822.png]]
1. Das **Repository** interagiert mit der **Room Datenbank** um auf die **Datenbankinstanz** zu zugreifen 
2. Das **Repository** erstellt **Entitäten** und befüllt diese mit Daten bevor sie an die **DAO** weiter gegeben wird.
3. Das **Repository** sendet Entitäten an die **DAO** um Entitäten einzufügen/bearbeiten oder nimmt welche entgegen als Ergebnis Suchanfragen.
4. Wenn die **DAO** Daten hat, die an das **Repository** gegeben werden sollen werden diese in **Entitäten** verpackt
5. Die **DAO** interagiert mit der **Room Database** um **Datenbankvorgänge** zu initiieren und Ergebnisse zu verarbeiten
## Repository
Wie bereits erwähnt, enthält das Repository den Code um die Daten aller **Datenquellen** zu verarbeiten. Dadurch wird vermieden das der **UI-Controller** oder das **ViewModel** direkt auf Datenquellen zugreifen müssen.  
## Room-Database
Dieses Objekt stellt eine **Schnittstelle** zwischen SQLite-Datenbank und Code bereit. Dabei sollte pro App maximal **eine** Room-Database vorhanden sein.  
## DAO
Das **DAO** enthält alle **SQL-Anweisungen** die das **Repository** benötigt um Daten in der **SQLite-Datenbank** zu manipulieren. Die Zuordnung erfolgt über **Annotationen** bei den entsprechenden **Methoden**.  
## Entitäten
Für jeden **Entitätstypen** wird eine Klasse erstellt. Diese Klasse enthält das Schema für jede Tabelle innerhalb der Datenbank. (**Tabellenname**, **Spaltenname**, deren **Datentyp**, **Primärschlüssel**)  
Zudem enthält jede Entität **Getter** und **Setter** über die später die Daten extrahiert werden können.  
Die Daten welche die **DAO** an das **Repository** zurück geben haben die Form einzelner **Instanzen** dieser Klasse.  
Wenn das **Repository** neue **Datensätze** schreiben muss erstellt es zuerst eine **Entität** und übergibt diese an das **DAO**.