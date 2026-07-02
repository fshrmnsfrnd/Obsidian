---
Thema:
  - "[[Python]]"
---
In Python werden Verzweigungen wie folgt dargestellt:  
```python
if x == y:
	print("Bedingung erfüllt!")
elif x == z:
	print("Bedingung x == z")
else:
	print("Bedinungen nicht erfüllt!")
```

- Die Anweisungen die bei einem wahren Ausdruck ausgeführt werden sollen sind zwingend einzurücken

## Vergleichsoperatoren

| Operator | Bedeutung      |
| -------- | -------------- |
| `==`     | gleich         |
| `!=`     | ungleich       |
| `>`      | größer         |
| `<`      | kleiner        |
| `>=`     | größer gleich  |
| `<=`     | kleiner gleich |
   
## Logische Operatoren
Die logischen Operatoren werden über die Wörter `and`, `or` und `nicht` dargestellt:  

```python
if (x==0 or ((y < 2) and (x > 2)):
	print("Bedingung erfüllt")
```
