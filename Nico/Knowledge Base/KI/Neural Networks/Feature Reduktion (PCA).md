---
Thema:
  - "[[Neural Networks]]"
  - "[[Sklearn]]"
---
>Principal Component Analysis

**Unsupervised-Learning-Verfahren**
- Ziel: **Dimensionsreduktion** bei gleichzeitiger Erhaltung möglichst vieler Informationen
- Beispiel:
    - Datensatz mit 1000 Features
    - Viele Features sind redundant, irrelevant oder verschlechtern das Modell
    - Reduktion z. B. auf 20 neue Features
## Funktionsweise der PCA
### 1. Varianz als Entscheidungsmaß
- PCA sucht Richtungen mit **maximaler Varianz**
- Größte Varianz = meiste Information
- Kleine Varianz = weniger relevante Information
### 2. Neue Feature-Achsen
- PCA erzeugt **neue Achsen (Hauptkomponenten)**
- Diese sind:
    - Lineare Kombinationen der ursprünglichen Features
    - Orthogonal zueinander

> [!NOTE] Es wird kein Feature einfach gelöscht
Es entstehen **Kombinationen mehrerer Features**
## Ziel der PCA
- **Abstände zwischen Datenpunkten** möglichst erhalten
- **Rekonstruktionsfehler minimieren**
- Möglichst viel Varianz mit möglichst wenigen Komponenten erklären
## Intuition (Geometrische Vorstellung)
- Datenpunkte liegen in einem mehrdimensionalen Raum
- Eine Richtung (z. B. u₁) zeigt große Streuung → wichtig
- Eine andere Richtung (z. B. v₁) zeigt geringe Streuung → weniger wichtig
- PCA projiziert Daten auf die wichtigsten Richtungen
## Standardabweichung (σ)
### Definition
- Maß für die **Streuung** von Werten um den Mittelwert (µ)
- Durchschnittliche Entfernung aller Werte vom Mittelwert
### Zusammenhang mit Varianz
- Varianz = σ²
- Große Varianz → große Streuung → wichtig für PCA
### Normalverteilung
- ~68 % der Werte liegen innerhalb von **1σ**
- ~95 % der Werte liegen innerhalb von **2σ**
# Code
---
```python
from sklearn.decomposition import PCA # Importieren der Module
pca = PCA(n_components=2) # Erstellt ein PCA welcher 2 Feature übrig lässt
#oder
pca = PCA(n_components=0.9) # Erstellt ein PCA welcher 90% Varianz behält

pca.fit(x) # Trainiert und Transformiert die Daten
x_pca = pca.transform(x)
print(f"Explained Variance Ratio:\n{pca.explained_variance_ratio_}")
print(f"Sum of Exmplained Variance Ratio:\n{sum(pca.explained_variance_ratio_)}")
```
