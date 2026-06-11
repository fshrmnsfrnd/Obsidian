---
Fach:
Thema:
  - "[[KI]]"
---
Ein neuronales Netz ist folgendermaßen aufgebaut:
![[Pasted image 20260304231555.png]]
# Multilayer Perception (MLP)
---
Damit man komplexere Aufgaben erledigen kann werden sogenannte [[Hidden Layer]] zwischen Ein- und Ausgabeschicht erstellt. Dabei gilt die richtige **Balance** zwischen **Komplexität** und **Rechenleistung** zu finden.  

> [!NOTE] Wenn es nur **ein [[Hidden Layer]]** gibt redet man von **Simple Neural Networks**, bei mehreren ist die Rede von **Deep Learning Neural Networks**!
# Training
---
- Man trainiert wie immer mit `x` und `y` Daten
- Die Differenz zwischen `y_predicted` und `y_test` ist der **Fehler**
- Den Fehler kann man verkleinern indem man die **Gewichte** anpasst
- Dafür verwendet man das [[Gradientenabstiegsverfahren]] 
## Ablauf des Trainings
- Ein Training besteht aus **mehreren Epochen**
- Eine Epoche ist der **komplette Trainingsdatensatz**
- Eine Epoche wird in mehrere (Mini)-**Batches** unterteilt 
- Dann wird ein Batch trainiert und anhand dessen der „stochastic gradient descent“ (**SGD**) berechnet
# Moderne Architekturen (Referenzwerte)
---
## Convolutional Neural Networks (CNNs) (z.B. Feedforward Neuronales Netz) 
| Modell | Schichten | Parameter |
| --- | --- | --- |
| **LeNet-5** | 2 Conv-Schichten | ~60.000 |
| **AlexNet** | 5 Conv-Schichten | ~60 Mio. |
| **VGG-16** | 16 | ~138 Mio. |
| **ResNet-50** | 50 | ~25 Mio. |
## [[Transformer]]-Modelle
| Modell | Schichten | Neuronen | Parameter |
| --- | --- | --- | --- |
| **BERT-Base** | 12 | 768 | ~110 Mio. |
| **GPT-3** | 96 | 12.288 | ~175 Mrd. |
| **GPT-4** | 120+ | | ~1,8 Bio. |