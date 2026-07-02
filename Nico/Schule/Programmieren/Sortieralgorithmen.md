---
Thema:
  - "[[Programmieren]]"
---
# [[Zeitkomplexität]]
---
## Vergleichsbasiertes Sortieren

| Sortieralgorithmus | Best-Case           | Average-Case          | Worst-Case          | Stabil | In-Place |
| ------------------ | ------------------- | --------------------- | ------------------- | ------ | -------- |
| Bubblesort         | $O(n)$              | $O(n^2)$              | $O(n^2)$            | Ja     | Ja       |
| Heapsort           | $O(n \cdot log(n))$ | $O(n \cdot log(n))$   | $O(n \cdot log(n))$ | Nein   | Ja       |
| Insertionsort      | $O(n)$              | $O(n^2)$              | $O(n^2)$            | Ja     | Ja       |
| Mergesort          | $O(n \cdot log(n))$ | $O(n \cdot log(n))$   | $O(n \cdot log(n))$ | Ja     | Nein     |
| Quicksort          | $O(n \cdot log(n))$ | $O(n \cdot log(n))$   | $O(n^2)$            | Nein   | Ja       |
| Selectionsort      | $O(n^2)$            | $O(n^2)$              | $O(n^2)$            | Nein   | Ja       |
| Shellsort          |                     | $O(n \cdot log(n)^2)$ | $O(n^1,25)$         | Nein   | Ja       |
## Adressiertes Sortieren

| Name         | Laufzeitkomplexität | Speicherplatzkomplexität | Stabil | In-Place |
| ------------ | ------------------- | ------------------------ | ------ | -------- |
| Bucketsort   | $O(n+k)$            | $O(n+k)$                 | Ja     | Nein     |
| Countingsort | $O(n+k)$            | $O(n+k)$                 | Ja     | Nein     |
| Radixsort    | $O(n \cdot l)$      | $O(n)$                   | Ja     | Nein     |
# Pseudocode
## Bubblesort
```python
x = 4, 5, 2, 89, 42, 69
laenge = x.Anzahl;
  for b = 1 to laenge
    for k = 0 to (laenge-b)
      if zahl[k] >  zahl[k+1]
        c = zahl [k]
        zahl[k] = zahl[k+1]
        zahl[k+1] = c
```
![[Pasted image 20251204111102.jpg]]

## Insertionsort
```python
l = 4, 5, 2, 89, 42, 69
for a in 0 -> l.length – 2
  do
      b = a + 1
      tmp = l[b]
      while b > 0 AND tmp < l[b-1] do
          l[b] = l[b-1]
          b – –
      l[b] = tmp
```
![[Pasted image 20251204111321.png]]

## Mergesort
### Unterteilen
```python
merge_sort (Liste a)
    if a <= 1
    do
      int mitte = a.lenght / 2
      int l -> i <= mitte – 1
      int r -> i >= array.length – mitte – 1
      l = merge_sort(l)
      r = merge_sort(r)
      return verschmelze(l,r)
```
### Verschmelzen
```python
verschmelze (l, r)
  int n
  int indexl = length(l) – 1
  int indexr = length(r) – 1
  int indergebnis = 0
    while indexl < l.length und indexr < r.length
    if l[indexl] < r[indexr]
  neul[indexergebnis] = l[indexl]
  indexl += 1
    else neul[indexergebnis] = r[indexr]
    indexr += 1
    indexergebnis += 1
  while indexl < l.length
    neul[indexergebnis] = l[indexl]
    indexl += 1
    indexergebnis += 1
  while (indexr < r.length)
    neul[indexergebnis] = r[indexr]
    indexr += 1
    indexergebnis += 1
  return neul
```

![[Pasted image 20251204111616.png]]

## Radixsort
![Radix Sort Beispiel, Radixsort Beispiel](https://blog.assets.studyflix.de/wp-content/uploads/2019/06/Radixsort-Beispiel-1-1024x576.jpg "Radix Sort Beispiel")

![[Pasted image 20251204111907.jpg]]

![[Pasted image 20251204111915.jpg]]

```java
class Radix_Sortieralgorithmus {
  public static void main (String[] args){
    int liste[] = {…};
    int i = liste.length;
    radixsort(liste, i);
    ausgeben(liste, i);
  }
   
  static int maximum(int liste[], int i){
    int max = liste[0];
    for (int a = 1; a < i; a++)
      if (liste[a] > max)
        max = liste[a];
      return max;
  }
   
   
  static void countingsort(int liste[], int i, int faktor){
    int ausgabe[] = new int[i];
    int a;
    int zaehlen[] = new int[10];
    Arrays.fill(zaehlen,0);
     
    for (a = 0; a < i; a++)
      zaehlen[ (liste[a]/faktor)%10 ]++;
    for (a = 1; a < 10; a++)
      zaehlen[a] += zaehlen[a – 1];
       
    for (a = i – 1; a >= 0; a–){
      ausgabe[zaehlen[ (liste[a]/faktor)%10 ] – 1] = liste[a];
      zaehlen[ (liste[a]/faktor)%10 ]–;
    }
     
    for (a = 0; a < i; a++)
      liste[a] = ausgabe[a];
     
    static void radixsort(int liste[], int i){
      int m = maximum(liste, i);
       
      for (int faktor = 1; m/faktor > 0; faktor *= 10)
      countingsort(liste, i, faktor);
    }
     
    static void ausgeben(int liste[], int i){
      for (int a=0; a<i; a++)
        System.out.print(liste[a]+“ „);
  }
```


## Quicksort
```python
funktion quicksort (li, re)
  if li < re
    t = teilen(li, re)
    quicksort(li, t)
    quicksort(t+1, re)
  end
end
 
funktion teilen(li, re)
  i = li – 1
  j = re + 1
  pivot = Liste[(li + re) / 2]
  while Liste[i] < pivot
    i++
  while Liste [j] > pivot
    j++
  if (i < j)
    int a = Liste[i]
    Liste[i] = Liste[j]
    Liste[j] = a
  else return j
```

![[Pasted image 20251204112415.jpg]]

## Heapsort
```python
Heapsort(arr) {
  BuildMaxHeap(arr)
  for i <- length(arr) downto 2 {
    tausche arr[1] <-> arr[i]
    heapsize <- heapsize -1
    Versickern(arr, 1)
  }
  
  BuildMaxHeap(arr) {
    heapsize <- length(arr)
    for i <- floor( length/2 ) downto 1
      Versickern(arr, i)
  }
    
  Versickern(arr, i) {
    l <- links(i)
    r <- rechts(i)
    if (l<=heapsize) and (arr[l]>arr[i])
      largest <- l
    else
      largest <- i
    if (r<=heapsize) and (arr[r]>arr[largest])
      largest <- r
    if (largest != i) {
      tausche arr[i] <-> arr[largest]
      Versickern(arr, largest)
    }
}
```

## Selectionsort
```python
Selectionsort (Liste l)
     For i = 0 to n-2
     Do
          Minimum = i
          For j = i + 1 to n-1
          Do
               If l[Minimum] > l[j] then Minimum = j
                    tmp = l[i]
                    l[i] = l[Minimum]
                    l[Minimum] = tmp
```
![[Pasted image 20251204112801.jpg]]
