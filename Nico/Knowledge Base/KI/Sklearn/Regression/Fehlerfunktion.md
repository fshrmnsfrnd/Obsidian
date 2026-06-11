---
Fach:
Thema:
  - "[[Regression]]"
  - "[[Sklearn]]"
---
Die Fehlerfunktion liefert gegenüber anderen [[Metrics]] einen festen Wert, der die Abweichung zwischen Implementierung und wahrem Wert wiedergibt. Anschließend kann überprüft werden, ob die Größe der Abweichung in gewissen Toleranzen liegt.
# R2 Score
---
- R²-Score (z.B. 0.71) ist keine Prozentangabe, sondern nur ein qualitativer Wert zur Modellbewertung
$$R^2 = 1 - \frac{\sum_{i}^{n}(y_i - \hat{y}_i)^2}{\sum_{i}^{n}(y_i - \bar{y})^2}$$

- $y_i$ = tatsächlicher Wert
- $\hat{y}_i$ = vorhergesagter Wert
- $\bar{y}$ = Mittelwert der tatsächlichen Werte

Der R² Score liegt zwischen $-\infty$ und 1, wobei 1 eine perfekte Vorhersage bedeutet.
```python
from sklearn.metrics import r2_score 
r2_score(y_true, y_pred, sample_weight=None, multioutput='uniform_average', force_finite=True)
```
# Mean absolute Percent Error (MAPE)
---
- MAPE zeigt den durchschnittlichen Vorhersagefehler eines Modells in Prozent an
$$MAPE = \frac{\sum \frac{|aktueller\_Wert - vorhergesagter\_Wert|}{|aktueller\_Wert|} \times 100}{Anzahl\_angepasster\_Punkte}$$
```python
from sklearn.metrics import mean_absolute_percentage_error
mean_absolute_percentage_error(y_true, y_pred, *, sample_weight=None, multioutput='uniform_average')
```
# Mean Square Error (MSE)
---
- Misst die durchschnittliche quadrierte Abweichung der Punkte von der Regressionsgeraden (Fehler werden quadriert und gemittelt).  
- Das Quadrieren entfernt Vorzeichen und gewichtet größere Fehler stärker.  
- Niedrigerer MSE = bessere Prognose, allerdings sehr empfindlich gegenüber Ausreißern.
$$MSE = \frac{\sum aktuellerWert - vorhergesagterWert}{n}$$
```python
from sklearn.metrics import mean_squared_error 
mean_squared_error(y_true, y_pred, *, sample_weight=None, multioutput='uniform_average', squared=True)
```
# Mean Absolute Error (MAE)
---
- Mittlerer absoluter Fehler (MAE): misst die durchschnittliche Größe der Vorhersagefehler ohne Berücksichtigung der Richtung.  
- Berechnung: Durchschnitt der absoluten Differenzen zwischen vorhergesagten und tatsächlichen Werten.  
- Zweck: Zur Bewertung der Genauigkeit von Regressionsmodellen; einfach interpretierbar.
$$MAE = \frac{1}{n}\sum_{i=1}^{n} \left|y_i - \hat{y}_i\right|$$
- $n$ = Anzahl der Datenpunkte  
- $y_i$ = tatsächlicher Wert  
- $\hat{y}_i$ = vorhergesagter Wert
```python
from sklearn.metrics import mean_absolute_error 
mean_absolute_error(y_true, y_pred, *, sample_weight=None, multioutput='uniform_average')
```
