---
Fach:
Thema:
  - "[[KI]]"
---
# [[Knowledge Base/KI/Sklearn/Datasets|Datasets]]
---
Zuerst muss ein [[Knowledge Base/KI/Sklearn/Datasets|Dataset]] geladen werden.
# [[Clustering]]
---
Wenn das Dataset keine y Daten (Klassen) enthält, müssen diese zuerst mit einem [[Clustering| Clustering Algorithmus]] ermittelt werden 
# [[Classifier]]
---
Dann kann ein [[Classifier]] damit trainiert werden.
Die Variable in der der [[Classifier]] gespeichert wird, wird normalerweise `clf` genannt.
## Bestimmung der Parameter
Um die besten Parameter für einen [[Classifier]] zu finden kann [[GridSearch]] oder [[RandomSearch]] verwendet werden.
Random Search ist die praxistauglichere Methode, da deutlich weniger gerechnet werden muss und annähernd gute Ergebnisse wie bei Grid Search kommen.

# Überprüfung der Daten
---
Um den [[Classifier]] zu testen, werden die Testdaten verwendet. Zum Testen können verschiedene [[Metrics|Metrics]] verwendet werden.
# Klassifizieren eines neuen Datenpunktes
---
Dies funktioniert bei allen mir bekannten Classifiern gleich:
```python
y_pred = clf.predict(x_test)
print(f"y_pred:\n{y_pred}")
```

# Speichern des Classifiers
---
Mit [[Speichern und Laden|Pickle]] 