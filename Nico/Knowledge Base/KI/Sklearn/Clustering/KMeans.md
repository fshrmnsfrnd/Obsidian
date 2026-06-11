---
Thema:
  - "[[Clustering]]"
  - "[[Sklearn]]"
---
>KMeans ist ein [[Classifier]] Algorithmus

# Theoretische Funktionsweise
---
>Bei KMeans sind die `y` [[Knowledge Base/KI/Sklearn/Datasets|Daten]] nicht bekannt. KMeans bestimmt die Mittelpunkte der Klassen. 
>Die Anzahl der Klassen ist dabei vorgegeben.

Die optimale Anzahl an Clustern kann mit der [[Elbow Chart Funktion]] herausgefunden werden.
## Algorithmus
1. **Initialisierung**
	- Zuerst wird die Anzahl der gewünschten Cluster k festgelegt. Anschließend werden zufällig k Clusterzentren (Mittelpunkte) im Datensatz platziert. 
2. **Zuordnung**
	- Jeder Datenpunkt wird dem Cluster zugeordnet, dessen Zentrum für ihn am nächsten liegt. Der euklidische Abstand 1 wird hierfür meist als Maß herangezogen. 
3. **Neuberechnung der Zentren**
	- Nachdem alle Datenpunkte zugeordnet wurden, wird für jedes Cluster ein neues Zentrum berechnet. Dieses neue Zentrum ist der Durchschnitt (Mittelwert) aller Datenpunkte, die dem jeweiligen Cluster zugeordnet wurden. 
4. **Wiederholung**
	- Die Schritte 2 und 3 werden so lange wiederholt, bis sich die Clusterzentren nicht mehr signifikant verschieben und die Datenpunkte stabil den Clustern zugeordnet sind.

# Programmierung
---
## Import
---
```python
from sklearn.cluster import KMeans
```

## Erstellen des KMeans Objekts
---
```python
class KMeans(  
	n_clusters: Int = 8,  
	*,  
	init: MatrixLike | ((...) -> Unknown) | Literal['k-means++', 'random'] = "k-means++",  
	n_init: int | Literal['auto', 'warn'] = "warn",  
	max_iter: Int = 300,  
	tol: Float = 0.0001,  
	verbose: Int = 0,  
	random_state: Int | RandomState | None = None,  
	copy_x: bool = True,  
	algorithm: Literal['lloyd', 'elkan', 'auto', 'full'] = "lloyd"  
)
```
**Beispiel:**
```python
clf = KMeans(n_clusters=2, random_state=0, n_init="auto")
```
### Parameter
| **Parameter** | **Bedeutung**                                                                                                                                                          | **Mögliche Werte**     |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| `n_cluster`   | die Anzahl der gewünschten Klassen                                                                                                                                     | `number`               |
| `init`        | `k-means++`: auswahl der Startwerte durch Stichprobenverfahren auf Basis einer empirischen Wahrscheinlichkeitsverteilung  <br>`random`: wählt zufällige Startwerte aus | `k-means++` / `random` |
| `n_init`      | Anzahl der Durchkäufe des k-menas Algorithmus  <br>bei `auto` und `init="k-means++"` 1 durchlauf  <br>bei `auto` und `init="random"` 10 durchkäufe                     | `number` / `auto`      |
| `max_iter`    | Maximale anzahl an Iterationen des Algorithmus                                                                                                                         | `number`               |
## Trainieren des Classifiers
---
```python
clf.fit(X)
clf.labels_ #Bestimmte Klassen für jeden Punkt
clf.cluster_centers_ #Cluster Mittelpunkte
```

## Einen Wert vorhersagen
---
```python
clf.predict(x)
```

## Visualisierung der Clusteranzahl
---
```python
from Elbow_Chart_Funktion import create_elbow_chart
create_elbow_chart(x, 10)
kmeans_estimator,ineritas = create_elbow_chart(X=X, max_clusters=10, random_state=42)
```
[[Elbow Chart Funktion]]

