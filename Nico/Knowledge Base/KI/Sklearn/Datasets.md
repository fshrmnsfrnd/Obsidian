---
Fach:
Thema:
  - "[[KI]]"
  - "[[Sklearn]]"
---
# Theorie
---
![[Datasets 2025-10-17 11.04.16.excalidraw]]
**Funktion:**
`x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.3)`

1. Daten mischen
2. Aufteilen zwischen Trainingsdaten und Testdaten
**X Matrix:**
Die Daten mit denen trainiert/getestet werden soll selbst

**Y Matrix:**
Die Kategorien in die die Daten klassifiziert werden sollen
# Import
---
```python
from sklearn import datasets
from sklearn.model_selection import train_test_split
```

# Einlesen vordefinierter Datasets
---
**Ausführlich:** 
(Wenn nicht nur die Daten sondern auch Beschreibung usw. gebraucht wird)
```python
iris = datasets.load_iris() #Z.B. die Iris Daten
x = iris.data
y = iris.target
class_names = iris.target_names
description = iris.DESCR
...
```
Hier am Beispiel `Iris`, es gibt aber noch viele andere.

**Kurz:**
(Wenn nur die Daten gebraucht werden)
```python
x, y = datasets.load_iris(return_X_y=True)
```

# Einlesen eigener Daten aus CSV
---
Hier sollten die `.csv` Dateien im selben Verzeichnis liegen
```python
import numpy as np
x=np.loadtxt('x_dataset.csv',delimiter=',')
y=np.loadtxt('y_dataset.csv',dtype='int64', delimiter=',')
```

# Beispieldaten anzeigen
---
```python
num_samples = x.shape[0]
num_features = x.shape[1]
print(f"num_samples: {num_samples}")
print(f"num_features: {num_features}")
```

# Aufteilen und Mischen des Datasets
---
Normalerweise nimmt man 30% Testdaten und 70% Trainingsdaten
```python
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.3)
```
# Normalisieren des Datasets
---
Man reduziert den Wertebereich behält dabei aber die Abstände (Relation/Korrelation) zwischen den Punkten bei. Alle Daten, die das Modell ab da verwendet müssen normalisiert sein (Training, Test, Prediction) 
> [!WARNING] Die `y`-Daten dürfen nicht normalisiert werden! 

Es gibt 2 Arten von Scalern:
## Min Max Scaler
- Wenn die Daten nicht als Normalverteilung vorliegen
- Neuronale Netze funktionieren mit Min Max Scaler besser
$$
x_{scaled} = \frac{x-x_{min}}{x_{max} - x_{min}}
$$
```python
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split

scaler = MinMaxScaler()
scaler.fit(x)
x_transformed = scaler.transform(x)
x_train, x_test, y_train, y_test = train_test_split(x_transformed, y, test_size=0.3)
```
## Standard Scaler
- Ziel dass die Werte einen Mittelwert von 0 und eine Standardabweichung von 1 haben
- Wenn die Daten normalverteilt sind oder einer Gaußschen Verteilung folgen
$$x_{scaled} = \frac{x - \mu}{\sigma}$$
Wobei $\mu$ der Mittelwert und $\sigma$ die Standardabweichung ist.
```python
from sklearn.preprocessing import StandardScaler 

scaler=StandardScaler()  
scaler.fit(x)
x_transformed=scaler.transform(x) 
x_train, x_test, y_train, y_test = train_test_split(x_transformed, y, test_size=0.3)
```
# Datasets generieren
---
## Import
```python
from sklearn.datasets import make_classification
```

## Generieren
>Generate a random n-class classification problem.
```python
x,y = make_classification(
	n_samples: Int = 100,  
	n_features: Int = 20,  
	*,  
	n_informative: Int = 2,  
	n_redundant: Int = 2,  
	n_repeated: Int = 0,  
	n_classes: Int = 2,  
	n_clusters_per_class: Int = 2,  
	weights: ArrayLike | None = None,  
	flip_y: Float = 0.01,  
	class_sep: Float = 1,  
	hypercube: bool = True,  
	shift: ArrayLike | None = 0,  
	scale: ArrayLike | None = 1,  
	shuffle: bool = True,  
	random_state: Int | RandomState | None = None
)
```
