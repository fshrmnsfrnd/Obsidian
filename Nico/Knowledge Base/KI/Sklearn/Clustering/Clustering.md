---
Fach: "[[KI]]"
---
Wenn die Y-Daten des [[Knowledge Base/KI/Sklearn/Datasets]] fehlen (was in der Praxis oft der Fall ist) kann man diese Klassen mit einer der folgenden Methoden erhalten.

- [[Gaussian Mixture Modell (GMM)]]
- [[KMeans]]

## GMM vs k-means

|               | **k-means**                                                                                                                                                                                                                                                                 | **GMM**                                                                                                                                                                                                                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Zuordnung** | feste Zuordnung (1 Punkt = 1 Cluster)                                                                                                                                                                                                                                       | weiche/stochastische Zuordnung (1 Punkt = 1 Wahrscheinlichkeit pro Cluster)                                                                                                                                                                                                                           |
| **Verwenden** | - Cluster sind annähernd kugelförmig  <br>- Cluster sind ähnlich groß  <br>- Runde Gruppen mit gleicher Varianz  <br>- es wird eine schnelle, günstige und Skalierbare Methode für große Datensätze benötigt  <br>- es wird eine leicht interpretierbare Zentroide benötigt | - Cluster sind elliptisch  <br>- Cluster haben unterschiedliche Größe, Orientierung oder Kovarianz  <br>- Wenn weiche Zuordnung benötigt wird  <br>- Überlappende Cluster  <br>- Wahrscheinlichkeit von Außreiser berechnen  <br>- bedingte Clusterdichte berechnen  <br>- Log-Likelihooods berechnen |
