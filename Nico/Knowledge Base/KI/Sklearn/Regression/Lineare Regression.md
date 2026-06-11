---
Fach:
Thema:
  - "[[Regression]]"
  - "[[Sklearn]]"
---
- Vorhersage von Werten (z.B. 3,5) statt Klassenzugehörigkeit
- Funktioniert auch mehrdimensional mit mehreren Features
- Es wird die Funktion einer Gerade erstellt die möglichst nah an allen Trainingsdatenpunkten vorbeikommt
- Training erfolgt durch Minimierung des Abstands zwischen Datenpunkten und Geraden
![[Pasted image 20260304180604.png]]

```python
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(
	dataset.data, dataset.target, test_size=0.2, random_state=42
)
regr = LinearRegression()
regr.fit(x_train, y_train)
r2_score = regr.score(x_test, y_test)

print(f"Coef:\n{regr.coef_}")
print(f"Intercept: {regr.intercept_}")
print(f"R2-Score: {r2_score}") # Umso näher an 1 umso besser. Unter 0 = Katastrophe

print(regr.predict([[3245, 4325, 2345, 4325]]))
```