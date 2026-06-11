---
tags:
Fach: "[[DB]]"
Thema:
  - "[[Relational Databases]]"
---
**Beispieltabelle**

| Pers_Nr | Name               | Hobby           | Geburtsdatum | Alter |
| ------- | ------------------ | --------------- | ------------ | ----- |
| 1       | ==Lorenz, Sophia== | ==Lesen, Kino== | 1.1.1990     | 34    |

# 1. Normalform
---
> [!INFO] 
> Alle Werte sind atomar.
> Meistens werden Spalten hinzugefügt.

>**Definition**:
>Eine Relation ist in der ersten Normalform, wenn die Werte der Attribute elementar (atomar) sind und keine Wiederholungsgruppen enthalten.
#### Überführung in die 1. Normalform
1. Für jedes atomare Attribut wird eine Spalte angelegt. 
2. Attribute mit nicht–atomaren Attributwerten werden in mehrere Attribute aufgeteilt. 
3. Jeder Wert einer Wiederholungsgruppe wird in eine eigene Zeile geschrieben.

Beispiel:

| Pers_Nr | VName  | NName  | Geburtsdatum | Alter | Hobby |
| ------- | ------ | ------ | ------------ | ----- | ----- |
| 1       | Sophia | Lorenz | 1.1.1990     | 34    | Lesen |
| 1       | Sophia | Lorenz | 1.1.1990     | 34    | Kino  |
# 2. Normalform
---
> [!INFO]
> Alle Datensätze haben einen eigenen Primary Key
> Meistens werden Tabellen hinzugefügt

>**Definition**:
>Eine Relation ist genau dann in der zweiten Normalform, wenn die 1NF erfüllt ist und jedes Nichtschlüsselattribut vom gesamten Schlüssel voll funktional abhängig ist.
#### Überführung in die 2. Normalform
1. Bestimme den Primärschlüssel.
2. Finde Attribute, die nur von einem Teil des Primärschlüssels abhängig sind.
3. Definiere eine neue Tabelle und übertrage die Attribute aus den vorherigen Schritt.
4. Entferne jetzt die übertragenen Attribute aus der ursprünglichen Tabelle.
5. Der Schlüssel-Teil, von dem diese Attribute abhängig sind, wird zum Primärschlüssel der neuen Tabelle.
6. Der Primärschlüssel der neuen Tabelle wird der Fremdschlüssel der ursprünglichen Tabelle.

**Person**

| Pers_Nr | VName  | NName  | Geburtsdatum | Alter |
| ------- | ------ | ------ | ------------ | ----- |
| 1       | Sophia | Lorenz | 1.1.1990     | 34    |
**Hobby**

| Hobby_Nr | Name  |
| -------- | ----- |
| 1        | Lesen |
| 2        | Kino  |
**Link_Person_Hobby**

| Pers_Nr | Hobby_Nr |
| ------- | -------- |
| 1       | 1        |
| 1       | 2        |
# 3. Normalform
---
> [!INFO] 
> Abhängige bzw. erschließbare oder berechenbare Werte löschen 

>**Definition**:
>Eine Relation (Tabelle) ist in der dritten Normalform, wenn die 2NF erfüllt ist und alle Nichtschlüsselattribute voneinander funktional unabhängig sind bzw. kein Nichtschlüsselattribut vom Schlüssel transitiv abhängt.

#### Überführung in die 3. Normalform
##### Das abhängige Nichtschlüsselattribut kann aus dem anderen Nichtschlüsselattribut berechnet werden:
- Entferne das abhängige Nichtschlüsselattribut.
- Die Berechnung erfolgt bei der Abfrage der Daten.
##### Sonst
- Definiere eine neue Tabelle.
- Das Nichtschlüsselattribut, von dem das andere Nichtschlüsselattribut abhängt, wird zum Primärschlüssel der neuen Tabelle. 
- Kopiere alle abhängigen Nichtschlüsselattribut in die neue Tabelle. 
- Entferne aus der ursprünglichen Tabelle alle abhängigen Nichtschlüsselattribute.
- Der Primärschlüssel der neuen Tabelle wird 'Fremdschlüssel' in der ursprünglichen Tabelle.

**Person**

| Pers_Nr | VName  | NName  | Geburtsdatum | ==Alter== |
| ------- | ------ | ------ | ------------ | --------- |
| 1       | Sophia | Lorenz | 1.1.1990     | ==34==    |
>==Alter== kann gelöscht werden, da es durch das Geburtsdatum berechnet werden kann