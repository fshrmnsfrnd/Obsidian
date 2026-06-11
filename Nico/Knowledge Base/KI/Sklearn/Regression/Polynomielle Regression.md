---
Fach:
Thema:
  - "[[Regression]]"
  - "[[Sklearn]]"
---
Wie [[Lineare Regression]] nur mit Polynom n-ten Grades statt Gerade
![[Pasted image 20260304181341.png]]
$$𝑃(𝑥) = 𝑎_𝑛 ∗ 𝑥^𝑛 + ⋯ +𝑎_3 ∗ 𝑥^3 + 𝑎_2 ∗ 𝑥^2 + 𝑎_1 ∗ 𝑥 + 𝑎_0$$ Wobei $a$ die Gewichte sind
$$𝑃(𝑥) = ∑^n_{i=0}𝑎_𝑖 ∗ 𝑥^𝑖$$
mit $𝑛 ∈ ℕ_0$ 
```python
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression

pf = PolynomialFeatures(degree=2) #Erzeugen des Objekts mit dem Grad des Polynom 
pf.fit(x_train) #Bestimmung der Anzahl der zu berechnenden Features
x_train_transformed = pf.transform(x_train) #Transformieren der Daten 
x_test_transformed = pf.transform(x_test)

poly_regr = LinearRegression() 
poly_regr.fit(x_train_transformed, y_train) 

r2_score = poly_regr.score(x_test_transformed, y_test) 
print(f"R2-Score: {r2_score}")
```
# Wahl des Grades
---
Wie bei knn mit den k-nächsten Nachbarn dient hier der Grad des Polynoms als Faktor, der beeinflusst werden kann. D.h. je nach Grad kann die Lineare Regression besser aber auch schnell sehr viel schlechter werden. Vergleicht man ein Polynom 2-Grades mit einem Vektor mit einem Feature bzw. mit zwei Feature erkennt man relativ schnell, wie schnell die Feature Anzahl ansteigt: 
1-Feature->3-Feature 
2-Feature -> 6-Feature 
Ein Polynom 10-Grades ist deswegen nicht besser. Allgemein hängt die Wahl des Grades wieder vom Datensatz ab und muss er testet werden
# Visualisierung
---
```python
import numpy as np
from matplotlib import pyplot as plt
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
  
def f(x: np.ndarray) -> np.ndarray:
    return -(x**4) * np.sin(x)
  
x = np.arange(start=0.0, stop=10.0, step=0.2).reshape(-1, 1)     #Wir benötigen Shape (xxx,1)
y = f(x)          #-1 sorgt dafür das alle Daten in Zeilen geshaped werden z.B. 600-> (600,1)
  
colors = ["blue", "red", "green", "magenta"]
def plot_poly_reg(x_original: np.ndarray, y_original: np.ndarray, degree: int) -> None:
    # Preprocessing
    pf = PolynomialFeatures(degree=degree)
    pf.fit(x_original)
    x_transformed = pf.transform(x_original)
    poly_regr = LinearRegression()
    poly_regr.fit(x_transformed, y_original)
    r2_score = poly_regr.score(x_transformed, y_original)
    print(f"Score: {r2_score} for degree: {degree}")
    print(f"Coef: {poly_regr.coef_}")
    print(f"Intercept: {poly_regr.intercept_}")
    y_pred = poly_regr.predict(x_transformed)
    # Plotting
    _ = plt.figure(figsize=(8, 8))                          #Plotgröße festlegen
    plt.plot(x_original, y_original, color="lightblue", linewidth=2, label="GT")
    plt.scatter(x_original, y_original, color="white", s=20, marker="o", label="Dataset")
    plt.plot(
        x_original,
        y_pred,
        color=colors[degree - 1],
        linewidth=2,
        label=f"Degree {degree}",
    )
    plt.show()
for degree in [1, 2, 3]:
    plot_poly_reg(x, y, degree)
```