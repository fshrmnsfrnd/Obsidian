---
Thema:
  - "[[Neural Networks]]"
  - "[[Sklearn]]"
---
# imports
---
```python
import numpy as np
np.random.seed(42)
import tensorflow as tf
tf.random.set_seed(42)
from tensorflow import keras
from sklearn.model_selection import train_test_split
from keras.layers import Activation     #Import Modul für die Aktivierungsfunktion
from keras.layers import Dense          #Anzahl der Dichte der "Neuronen"
from keras.models import Sequential     #Modul zum Erzeugen des Neuronalen Netzes
from keras.optimizers import SGD        #Import Modul Stochastic Gradient Decent
from keras.utils import to_categorical  #Converts a class vector to binary class matrix.
```
# Daten laden
---
```python
dataset = load_digits()
x = dataset.data
y = dataset.target

y_cat=to_categorical(y,num_classes=10) #denke optional

x_train, x_test, y_train, y_test = train_test_split(x, y_cat, test_size=0.30)
```
# Daten normalisieren
---
![[Knowledge Base/KI/Sklearn/Datasets#Normalisieren des Datasets|Datasets]]
# Neuronales Netz bauen
---
```python
from keras import layers
from tensorflow.keras.layers import Activation
from tensorflow.keras.layers import Dense
from tensorflow.keras.models import Sequential
from tensorflow.keras.optimizers import SGD

model = Sequential()
model.add(layers.Input(shape=(x.shape[1],),name='Eingabeschicht'))
model.add(Dense(units=450,name='Erste_verdeckte_Schicht'))           #Neuronen
model.add(Activation("relu",name='Aktivierungsfunktion_Schicht1'))   #Aktivierungsfunktion
model.add(Dense(units=450,name='Zweite_verdeckte_Schicht'))
model.add(Activation("relu",name='Aktivierungsfunktion_Schicht2'))
model.add(Dense(units=3,name='Ausgabeschicht'))
model.add(Activation("softmax",name='Aktivierungsfunktion_der_Ausgabeschicht'))
```
# Modell anzeigen lassen
---
```python
model.summary()
```
Model: "sequential"
<pre style="white-space:pre;overflow-x:auto;line-height:normal;font-family:Menlo,'DejaVu Sans Mono',consolas,'Courier New',monospace">┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┓
┃<span style="font-weight: bold"> Layer (type)                    </span>┃<span style="font-weight: bold"> Output Shape           </span>┃<span style="font-weight: bold">       Param # </span>┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━┩
│ Hidden_Layer1 (<span style="color: #0087ff; text-decoration-color: #0087ff">Dense</span>)           │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">512</span>)            │        <span style="color: #00af00; text-decoration-color: #00af00">33,280</span> │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ Aktivierungsfunktion_Hidden_La… │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">512</span>)            │             <span style="color: #00af00; text-decoration-color: #00af00">0</span> │
│ (<span style="color: #0087ff; text-decoration-color: #0087ff">Activation</span>)                    │                        │               │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ Hidden_Layer2 (<span style="color: #0087ff; text-decoration-color: #0087ff">Dense</span>)           │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">256</span>)            │       <span style="color: #00af00; text-decoration-color: #00af00">131,328</span> │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ Aktivierungsfunktion_Hidden_La… │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">256</span>)            │             <span style="color: #00af00; text-decoration-color: #00af00">0</span> │
│ (<span style="color: #0087ff; text-decoration-color: #0087ff">Activation</span>)                    │                        │               │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ Hidden_Layer3 (<span style="color: #0087ff; text-decoration-color: #0087ff">Dense</span>)           │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">128</span>)            │        <span style="color: #00af00; text-decoration-color: #00af00">32,896</span> │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ Aktivierungsfunktion_Hidden_La… │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">128</span>)            │             <span style="color: #00af00; text-decoration-color: #00af00">0</span> │
│ (<span style="color: #0087ff; text-decoration-color: #0087ff">Activation</span>)                    │                        │               │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense (<span style="color: #0087ff; text-decoration-color: #0087ff">Dense</span>)                   │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">10</span>)             │         <span style="color: #00af00; text-decoration-color: #00af00">1,290</span> │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ activation (<span style="color: #0087ff; text-decoration-color: #0087ff">Activation</span>)         │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">10</span>)             │             <span style="color: #00af00; text-decoration-color: #00af00">0</span> │
└─────────────────────────────────┴────────────────────────┴───────────────┘
</pre>
 Total params: 198,794 (776.54 KB)
 Trainable params: 198,794 (776.54 KB)
 Non-trainable params: 0 (0.00 B)
# Model kompilieren
---
- eine **Fehlerfunktion**: hier `categorical_crossentropy`  
- eine **Optimierung**: hier `SDG`  
- und eine an zu wendende **Metrik**: hier `accuracy`
```python
model.compile(
	loss="categorical_crossentropy", optimizer=SGD(), metrics=["accuracy"]
)
```
# Model trainieren
---
```python
model.fit(x=x_train, y=y_train, epochs=30, validation_data=(x_test,y_test))
```
# Speichern und Laden
---
```python
import keras
model.save("NeuronalesNetz.kaeras")
loaded_model = keras.models.load_model("NeuronalesNetz.kaeras")
```
# Weitere Schichten
---
##  [[Hidden Layer#Convolutions (Faltungs-) Layers|Convolutional Neural Networks]] (CNNs)
- **Conv1D**, **Conv2D**, **Conv3D**: Faltungsschichten für 1D, 2D oder 3D Daten  
- **SeperableConv2D**: Effizientere Variante der 2D-Faltung  
- **DepthwiseConv2D**: Faltung über räumliche Dimensionen
- **Conv2DTranspose**: Transponierte Faltung (für Upsampling)  
```python 
import keras
model.add(keras.layers.Conv2D(filters=32, kernel_size=(3,33)))
```
## [[Hidden Layer#Pooling Layers|Pooling Layers]]
- **MaxPooling1D**, **MaxPooling2D**, **MaxPooling3D**: Maximales pooling  
- **AveragePooling1D**, **AveragePooling2D**, **AveragePooling3D**: Durchschnittliches Pooling
- **GlobalMaxPooling2D**, **GlobalAveragePooling2D**: Globales Pooling über gesamte Feature Maps.
```python
import keras
model.add(keras.layers.MaxPooling2D(pool_size=(22, 2)))
```
# [[Hidden Layer#Recurrent (Wiederholungs-) Layers|Recurrent Layers]]
- **Simple RNN**: Einfache rekurrente Schicht  
- **LSTM**: Long Short-Term Memory  
- **GRU**: Gated Recurrent Unit  
- **Bidirectional**: Wrapper für bidirektionale RNNs  
- **ConvLSTM2D**: Kombination aus CNN und LSTM  
```python
import keras
model.add(keras.layers.LSTM(128))
```
## [[Hidden Layer#Normalization Layers|Normalization Layers]]
- **Batch Normalization**: Normalisiert Aktivierungen über Batch  
- **Layer Normalization**: Normalisiert über Features  
- **Group Normalization**: Normalisiert Gruppen von Kanälen  
- **Unit Normalization**: Normalisiert auf Einheitslänge  
```python
import keras
model.add(keras.layers.Normalization(axis=-1, mean=None, variance=None, invert=False))
```
## [[Hidden Layer#Regularization Layers|Regularization Layers]]
- **Dropout**: Zufälliges Deaktivieren von Neuronen  
- **SpatialDropout1D/2D/3D**: Dropout ganzer Feature-Maps  
- **GaussianDropout**: Dropout mit Gaußschem Rauschen  
- **GaussianNoise**: Fügt Gaußsches Rauschen hinzu  
- **AlphaDropout**: Spezielles Dropout für SELU-Aktivierung  
```python
import keras
model.add(keras.layers.Dropout(rate=0.25))
```
## [[Hidden Layer#Reshaping Layers|Reshaping Layers]]
- **Flatten**: Flacht mehrdimensionale Eingaben ab  
- **Reshape**: Ändert die Form der Daten  
- **Permute**: Vertauscht Dimensionen  
- **RepeatVector**: Wiederholt Eingabe n-mal  
- **Cropping1D/2D/3D**: Schneidet Dimensionen zu  
- **UpSampling1D/2D/3D**: Vergrößert räumliche Dimensionen  
- **ZeroPadding1D/2D/3D**: Fügt Nullen hinzu  
```python
import keras
model.add(keras.layers.Flatten())
```
## [[Hidden Layer#Merging Layers|Merging Layers]]
- **Concatenate**: Verbindet Tensoren entlang einer Achse
- **Add**: Addiert mehrere Tensoren 
- **Subtract**: Subtrahiert Tensoren  
- **Multiply**: Multipliziert Tensoren elementweise  
- **Average**: Berechnet Durchschnitt mehrerer Tensoren  
- **Maximum/Minimum**: Elementweises Maximum/Minimum  
- **Dot**: Skalarprodukt  
```python
import keras
tf_keras.layers.Concatenate(axis=-1)
```
## [[Hidden Layer#Embedding Layers|Embedding Layers]]
- **Embedding**: Wandelt Integer-Indizes in dichte Vektoren um  
- **TextVectorization**: Vektorisiert Text (Preprocessing)  
```python
import keras
model.add(keras.layers.Embedding(input_dim=1000, output_dim=64))
```