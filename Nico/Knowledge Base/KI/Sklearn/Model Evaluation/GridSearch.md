---
Thema:
  - "[[Model Evaluation]]"
  - "[[Sklearn]]"
---
>Grid Search probiert alle Kombinationen der übergebenen Parameter auf dem übergebenen Classifier Algorithmus aus.
# Import
---
```python
from sklearn.model_selection import GridSearchCV
```

# Objekt erstellen
---
## Parameter erstellen
>Die Parameter müssen zum Algorithmus(z.B. [[DecisionTree]] oder [[KNeighbours]]) passen, auf den die GridSearch angewendet wird
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

## GridSearch erstellen
```python
GridSearchCV(
	estimator: _BaseEstimatorT@GridSearchCV, 
	param_grid: Mapping[Unknown, Unknown] | Sequence[dict[Unknown, Unknown]], 
	*, 
	scoring: ArrayLike | tuple[Unknown, ...] | ((...) -> Unknown) | Mapping[Unknown, 
	Unknown] | None = None, n_jobs: Int | None = None, refit: str | ((...) -> Unknown)
		| bool = True, cv: int | BaseCrossValidator | Iterable[Unknown] | None = None,
	verbose: Int = 0, 
	pre_dispatch: str | int = "2*n_jobs", 
	error_score: Float | str = ..., 
	return_train_score: bool = False
)
```
**Beispiel:**
```python
grid_cv = GridSearchCV(clf, parameters, cv=3, n_jobs=-1)
```

# Die besten Parameter finden
---
```python
grid_cv.fit(x_train, y_train)
print("Best Params:", grid_cv.best_params_)
```

# Bewerten der Genauigkeit
---
```python
best_score = grid_cv.best_score_
print("Best Tree Score", best_score * 100.0, "%")
```