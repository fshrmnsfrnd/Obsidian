---
Fach:
Thema:
  - "[[KI]]"
  - "[[Sklearn]]"
---
Manchmal ist es nötig mehrere verschiedene Kombinationen von Algorithmen zu kombinieren. Damit dies möglich ist verwendet man **Pipelines**. Diese Pipelines können dann mit Parametern (`schrittname__parametername`) an z.B. ein Grid Search übergeben werden

```python
from sklearn.model_selection import GridSearchCV
from sklearn.pipeline import Pipeline

pipe=Pipeline(steps=[('pf',PolynomialFeatures()),('reg',LinearRegression())])

params={'pf__degree':[2,3,4]}
grid = GridSearchCV(pipe,params ,cv=5, n_jobs=-1)
grid.fit(x_train, y_train)
print(grid.best_params_)
bestclf = grid.best_estimator_
print(bestclf.predict([[ 1.58120000e+00,2.40000000e+01,4.19520056e+00,1.02278412e+00 , 1.33200000e+03 , 3.87543733e+00 , 3.60500000e+01 ,-1.29010000e+02]]))

bestPipe = Pipeline(steps=[('pf',PolynomialFeatures()),('reg',LinearRegression())])
bestPipe.set_params(pf__degree=2)
bestPipe.fit(x_train, y_train)
```
