---
Thema:
  - "[[Neural Networks]]"
---
# Anzahl der verdeckten Schichten 
---
- 1 Schicht: Für einfache, linear separierbare Probleme ([[Lineare Regression]]) 
- 2-3 Schichten: Für die meisten praktischen Anwendungen ausreichend 
- 4+ Schichten: Für komplexe Muster (**Deep Learning**) wie Bild- oder Spracherkennung

> [!NOTE] Grundregel
> Beginnen Sie mit 1-2 verdeckten Schichten und erhöhen Sie deren Anzahl nur bei Bedarf.
# Anzahl der [[Neuronen]] pro Schicht
---
Es gibt mehrere Ansätze:
1. **Durchschnitt In und Output**
	Anzahl Neuronen = $\frac{Input_{Neuronen} + Output_{Neuronen}}{2}$ 
2. **2/3 Regel**
	Neuronen = $\frac{2}{3}\times(Input_{Neuronen} + Output_{Neuronen})$ 
3. **Kleiner als Input**
	Neuronen < 2 * Input-Neuronen
4. **Pyramidenform**
	Jede Schicht hat weniger als die Vorherige
## Aufgabenspezifische Empfehlungen 
| Aufgabentyp                 | Schichten | Neuronen pro Schicht | Beispiel             |
|----------------------------:|:---------:|:--------------------:|----------------------|
| Einfache Klassifikation     | 1-2       | 10-100               | Iris-Datensatz       |
| Regression                  | 1-2       | 10-50                | Hauspreisvorhersage  |
| Bilderkennung (klein)       | 2-5       | 64-512               | MNIST                |
| Bilderkennung (komplex)     | 10-100+   | 64-4096              | ImageNet (CNN)       |
| NLP (einfach)               | 2-3       | 128-512              | Sentiment-Analyse    |
| NLP (komplex)               | 12-96     | 768-12288            | GPT, BERT            |
| Zeitreihen                  | 2-3       | 50-200               | LSTM/GRU             |
## Praktische Entscheidungskriterien
Zu wenige Neuronen/Schichten (Underfitting)
- Symptome: Schlechte Performance auf Trainings- UND Testdaten
- Lösung: Mehr Neuronen/Schichten hinzufügen

Zu viele Neuronen/Schichten (Overfitting)
- Symptome: Gute Performance auf Trainingsdaten, schlecht auf Testdaten
- Lösungen:
  - Dropout (0.2–0.5)
  - Regularisierung (L1/L2) — verhindert Überanpassung an Trainingsdaten
  - Early Stopping (Callback; Training abbrechen, wenn Validierungsleistung verschlechtert)
  - Mehr Trainingsdaten

# Weitere Schichten
Zu den Normalen **Hidden Layers** gibt es auch andere Schichten welche andere Aufgaben erfüllen. 

|**Layer Typ**|**Anwendung**|
|---|---|
|Convolution Layer|Computervision, Bildverarbeitung|
|Pooling Layer|Dimensionsreduktion, Translationsinvarianz|
|Recurrent Layer|Zeitreihen, Sequenzen, Textverarbeitung, Spracherkennung|
|Normalization Layer|Stablisierung des Trainings, schnellere Konvergenz|
|Regularization Layer|Verhinderung ovn Overfitting|
|Reshaping Layer|Datenanpassung zwischen Schichten|
|Merging Layer|Skip-Connections, Multi-Input-Modelle, Ensemble-Methoden|
|Embedding Layer|NLP, Wort-[[Embeddings]], kategorial Features|
## Convolutions (Faltungs-) Layers
Diese so genanten **Faltungsschichten** sind die **Schlüsselbausteine** von sogenannten **CNNs** (Faltungsneuralen Netzen). Diese Netze werden für **Computervision** und **Bildverarbeitung** verwendet.  
Solche Layer können Muster wie z. B. **Kanten**, **Texturen** und **Formen** erkennen.  
Diese Filter werden erst beim Training erlernt und aktualisiert.  
## Pooling Layers
Pooling Layer verringern die Dimensionen ohne wichtige Informationen zu verlieren, das sorgt dafür das die Komplexität der Modelle klein bleiben.  
Z. B. können 4x4 Pixel auf 2x2 Pixel reduziert werden
## Recurrent (Wiederholungs-) Layers
**Recurrent Neural Networks** (**RNNs**) verarbeiten **sequentielle Daten**. Sie speichern Informationen über Zeitschritte hinweg, was sie für **Spracherkennung**, **maschinelle Übersetzung** und **Zeitreihenprognosen** benötigen.
## Normalization Layers
Hier werden:  
- **Redundanzen** in Datenbanken verringert um Speicherplatz zu sparen  
- **Datenintegrität** und **-konsistenz** inverbessert  
- **Konvergenzgeschwindigkeit** und **Genauigkeit** von Modellen in maschinellen Lernumgebungen erhöht.  
Das alles sorgt für **zuverlässigere Ergebnisse** und **effizientere arbeiten**
## Regularization Layers
Diese Schichten sorgen dafür das, das Overfitting verhindert wird. Sie fügen **Verlustfunktionen** und **Strafen für komplexe Modellparameter** ein.
=> Modelle bleiben **einfacher** und **allgemeiner**
## Reshaping Layers
Diese Schicht passt die Eingabedaten an. Wenn z. B. ein Netzwerk die Form "Batch_Size, Höhe, Breite, Kanäle" erwartet, aber die Daten in einem anderen Format sind, kann ein **Reshaping Layer** die Daten so umformen das es passt.  
Wenn die Daten im falschen Format wären, könnten beim Training Fehler entstehen und das Lernen von Mustern verschlechtern.
## Merging Layers
Wenn mehrere **parallele Teilnetze** oder **Schichten** Trainiert werden kann der **Output** von denen über so eine **Zusammenführschicht** wieder zu einem Output verbunden werden. Dies ermöglicht den Aufbau von **nicht Sequenziellen** Modellen.
## Embedding Layers
**Embedding Layer** können **Eingabeinformationen** von einem **hochdimensionalen** zu einem **niedrigerdimensionalen Raum** umwandeln. Dies wird z. B. in der **Spracherkennung** verwendet um die Komplexe Sprache zu **vektorisieren**.
## Spezielle Schichten
Es gibt noch weiter Schichten, ein Beispiel wäre eine **Lambda-Schicht** in der **benutzerdefinierte Operationen** stattfinden können:  
-> **Lambda**: Benutzerdefinierte Operationen  
-> **ActivityRegularization**: Regulierung der Aktivierungen  
-> **Masking**: Maskierte Zeitschritte in Sequenzen  
-> **TimeDistributed**: Wendet Schicht auf jedem Zeitschritt an