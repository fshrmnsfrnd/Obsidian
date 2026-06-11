---
Fach:
Thema:
  - "[[KI]]"
  - "[[Sklearn]]"
---
# Import
```python
import pickle
```
# Speichern
```python
with open('save_model.pkl','wb')as file: 
	pickle.dump(clf,file)
```

**Direkt das beste Classifier Objekt speichern:**
```python
with open('save_model.pkl','wb')as file: 
	pickle.dump(grid.best_estimator_,file)
```

# Laden
```python
with open('save_model.pkl','rb') as file: 
	loaded_clf=pickle.load(file)
```