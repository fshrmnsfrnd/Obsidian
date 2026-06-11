---
Thema:
  - "[[Model Evaluation]]"
  - "[[Sklearn]]"
---
# Theoretische Funktionsweise
---
Neben den Hyperparametern spielen die Test- und Trainingsdaten eine erhebliche Rolle bei der Bewertung.  Man teilt die Trainingsdaten in k-Bestandteile auf (z.B. k=5 hier Fold). Anschließend werden die k-Modelle (hier Split bzw. Iteration) trainiert. Dabei werden je Modell immer ein Fold als Testdaten benutzt. Abschließend ergibt sich für jedes dieser Modelle (Iteration) ein Score. Zuletzt bildet man den Mittelwert über alle Scores und erhält somit eine aussagekräftige Größe.

![[Pasted image 20251230192334.png]]
## [[GridSearch]]
Bei Grid Search erstellt man methodisch mehrere Modelle (wie ein Gitter) und wertet anschließend den Score aus. Anschließend wählt man das beste Modell und trainiert dies mit den Trainingsdaten. Abschließend erfolgt die Auswertung über den Score mit Hilfe der Testdaten. **Beispiel**: Bei KNN kann man hier über verschachtelte for-Schleifen verschiedene k-Werte in Kombination mit der Gewichtung (weights) distance oder uniform testen.
## [[RandomSearch]]
Bei Random Search werden zufällig verschiedene Modelle erstellt und anschließend der Score bewertet. Das beste Modell wird danach wieder mit den Trainingsdaten trainiert und mit den Testdaten der Score bestimmt. 
**Beispiel**: Bei KNN würde man nicht alle Kombinationen aus einem Intervall von 1 bis 100 testen, sondern beispielsweise nur 20, diese jedoch auch nicht mit allen Kombinationen aus distance und uniform.
# Programmieren
---
# Import
---
```python
from sklearn.model_selection import cross_val_score
```

# Berechnen des Scores
```python
cross_val_score(
	estimator: BaseEstimator,  
	X: MatrixLike,  
	y: MatrixLike | ArrayLike | None = None,  
	*,  
	groups: ArrayLike | None = None,  
	scoring: str | ((...) -> Unknown) | None = None,  
	cv: int | BaseCrossValidator | Iterable[Unknown] | None = None,  
	n_jobs: Int | None = None,  
	verbose: Int = 0,  
	fit_params: dict[Unknown, Unknown] | None = None,  
	pre_dispatch: Int | str = "2*n_jobs",  
	error_score: Float | str = ...
)
```
**Beispiel:**
```python
scores = cross_val_score(clf, x_train, y_train, cv=10)
```

## Parameter
---
- **estimator** : _estimator object implementing 'fit'_ 
	- The object to use to fit the data.
- **X** : _{array-like, sparse matrix} of shape (n_samples, n_features)_  
	- The data to fit. Can be for example a list, or an array.
- **y** : _array-like of shape (n_samples,) or (n_samples, n_outputs), default=None_
	- The target variable to try to predict in the case of supervised learning.
- **groups** : _array-like of shape (n_samples,), default=None_
	- Group labels for the samples used while splitting the dataset into train/test set. Only used in conjunction with a "Group" `cv` instance (e.g., `GroupKFold`).
- **scoring** : _str or callable, default=None_  
	- Strategy to evaluate the performance of the `estimator` across cross-validation splits.
	- str: see `scoring_string_names` for options.
	- callable: a scorer callable object (e.g., function) with signature `scorer(estimator, X, y)`, which should return only a single value. See `scoring_callable` for details.
	- `None`: the `estimator`'s `default evaluation criterion <scoring_api_overview>` is used.
	- Similar to the use of `scoring` in `cross_validate` but only a single metric is permitted.
- **cv** : _int, cross-validation generator or an iterable, default=None_  
	- Determines the cross-validation splitting strategy. Possible inputs for cv are:
		- `None`, to use the default 5-fold cross validation,
		- int, to specify the number of folds in a `(Stratified)KFold`,
		- `CV splitter`,
		- An iterable that generates (train, test) splits as arrays of indices.
	- For `int`/`None` inputs, if the estimator is a classifier and `y` is either binary or multiclass, `StratifiedKFold` is used. In all other cases, `KFold` is used. These splitters are instantiated with `shuffle=False` so the splits will be the same across calls.
	- Refer `User Guide <cross_validation>` for the various cross-validation strategies that can be used here.
- **n_jobs** : _int, default=None_  
	- Number of jobs to run in parallel. Training the estimator and computing the score are parallelized over the cross-validation splits. `None` means 1 unless in a `joblib.parallel_backend` context. `-1` means using all processors. See `Glossary <n_jobs>` for more details.
- **verbose** : _int, default=0_  
	- The verbosity level.
- **params** : _dict, default=None_  
	- Parameters to pass to the underlying estimator's `fit`, the scorer, and the CV splitter.
- **pre_dispatch** : _int or str, default='2*n_jobs'_  
	- Controls the number of jobs that get dispatched during parallel execution. Reducing this number can be useful to avoid an explosion of memory consumption when more jobs get dispatched than CPUs can process. This parameter can be:
		- `None`, in which case all the jobs are immediately created and spawned. Use this for lightweight and fast-running jobs, to avoid delays due to on-demand spawning of the jobs
		- An int, giving the exact number of total jobs that are spawned
		- A str, giving an expression as a function of n_jobs, as in '2*n_jobs'
- **error_score** : _'raise' or numeric, default=np.nan_  
	- Value to assign to the score if an error occurs in estimator fitting. If set to 'raise', the error is raised. If a numeric value is given, FitFailedWarning is raised.

