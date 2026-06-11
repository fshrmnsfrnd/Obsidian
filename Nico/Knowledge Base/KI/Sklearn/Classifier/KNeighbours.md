---
Thema:
  - "[[Classifier]]"
  - "[[Sklearn]]"
aliases:
  - KNN
---
>KNeighbours ist ein [[Classifier]] Algorithmus 
# Theoretische Funktionsweise
---
>KNN ist ein Classifier Algorithmus, der zu einem zu klassifizierenden Datenpunkt die k nächsten Nachbarn bestimmt. 
>K ist dabei eine Variable, die frei wählbar ist. Zum Beispiel könnte k=3 sein. Damit würden zu einem Datenpunkt die nächsten 3 Punkte bestimmt.

![[Pasted image 20251230185411.png]]

## Umsetzung
1. Bestimmung der Entfernung (Vektorgeometrie)
	- geg.: $\vec b, \vec c$ 
	- Abstand zwischen 2 Punkten
		- |$\vec P$| = $\vec c - \vec b$
		- |$\vec P$| = ($\sum^{n}_{i=1} a_i^2$)
2. Bestimmung für alle Datenpunkte
3. Sortieren der Entfernung und bestimmen der k-nächsten Nachbarn
4. Zu welcher Klasse gehören die k-nächsten Nachbarn
5. Welche Klasse ist am meisten vertreten?
	- Datenpunkt gehört auch zu dieser Klasse
# Programmierung
---
## Import
---
```python
from sklearn.neighbors import KNeighborsClassifier
```

## Erstellen eines KNeighbors Objekts
---
```python
KNeighborsClassifier(
	n_neighbors: Int = 5,  
	*=5,  
	weights: Unknown | ((...) -> Unknown) | Literal['uniform', 'distance'] = "uniform", 
	algorithm: Literal['auto', 'ball_tree', 'kd_tree', 'brute'] = "auto",  
	leaf_size: Int = 30,  
	p: Int = 2,  
	metric: str | ((...) -> Unknown) = "minkowski",  
	metric_params: Unknown | dict[Unknown, Unknown] = None,  
	n_jobs: Int | Unknown = None
)
```
### Parameter
|**Parameter**|**Bedeutung**|**Mögliche Werte**|
|---|---|---|
|`n_neighbors`|Anzahl der nächsten Nachbarn die Untersucht werden|`number`|
|`weights`|`uniform`: der Abstand der Datenpunkte bleibt unberücksichtigt  <br>`distance`: der Abstand der Datenpunkte wird berücksitigt|`"uniform"` / `"distance"`|

**Beispiel:**
```python
clf = KNeighborsClassifier(n_neighbors=3, weights='distance')
```
## Trainieren des Classifiers
---
```python
clf.fit(x_train, y_train)
```

## Bewerten der Genauigkeit
---
```python
accuracy = clf.score(x_test, y_test)
```

## Einen neuen Punkt klassifizieren
---
```python
y_pred = clf.predict(x_test)
```

