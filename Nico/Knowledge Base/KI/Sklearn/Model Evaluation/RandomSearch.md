---
Thema:
  - "[[Model Evaluation]]"
  - "[[Sklearn]]"
---
>Random Search erstellt zufällig verschiedene Modelle und bewertet anschließend den Score
>So muss weniger gerechnet werden als bei [[GridSearch]]
# Import
---
```python
from sklearn.model_selection import RandomizedSearchCV
```

# Objekt erstellen
---
## Parameter erstellen
>Die Parameter müssen zum Algorithmus(z.B. [[DecisionTree]] oder [[KNeighbours]]) passen, auf den die RandomSearch angewendet wird
```python
# Sample Params for DecisionTreeClassifier
parameters = {
    "criterion": ["gini", "entropy"],
    "max_depth": [2, 3, 4, 5, 6, 8, 10],
    "min_samples_split": [2, 4, 6],
    "min_samples_leaf": [1, 2],
    "max_features": ["sqrt", "log2"]
}
```

## Klassifikationsalgorithmus erstellen
```python
# z.B.
clf = DecisionTreeClassifier()
# oder
clf = KNeighborsClassifier()
```

## RandomSearch erstellen
```python
RandomizedSearchCV(
	_estimator_, 
	_param_distributions_, 
	_*_, 
	_n_iter=10_, 
	_scoring=None_, 
	_n_jobs=None_, 
	_refit=True_, 
	_cv=None_, 
	_verbose=0_, 
	_pre_dispatch='2*n_jobs'_, 
	_random_state=None_, 
	_error_score=nan_, 
	_return_train_score=False_)
```
**Beispiel:**
```python
rand_cv = RandomizedSearchCV(clf, param_distributions=parameters, n_iter=5, cv=3)
```

# Die besten Parameter finden
---
```python
rand_cv.fit(x_train, y_train)
print("Best Params:", rand_cv.best_params_)
```

# Bewerten der Genauigkeit
---
```python
best_score = rand_cv.best_score_
print("Best Tree Score", best_score * 100.0, "%")
```