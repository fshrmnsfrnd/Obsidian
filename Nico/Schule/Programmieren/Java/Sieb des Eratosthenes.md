---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Java]]"
---
# Funktionsweise
1. Es werden alle Zahlen von 2 bis N aufgeschrieben. Wir nehmen zunächst an, dass sie alle prim sind.
2. Die kleinste unmarkierte Zahl ist immer eine Primzahl. 
3. Nachdem eine Primzahl gefunden wurde, werden alle Vielfachen dieser Primzahl als nicht prim markiert. 
4. Dann wird die nächstgrößere unmarkierte Zahl bestimmt. Da sie kein Vielfaches sein kann (sonst wäre sie markiert worden), kann sie nur eine Primzahl sein.
5. Ist die kleinste Zahl kleiner oder gleich der Wurzel von N, geht es weiter bei Schritt 3.
6. Nun müssen noch die Primzahlen ausgeben werden, die größer als Wurzel(N) sind: Das sind die, die noch nicht gestrichen wurden.
![[Pasted image 20251210120749.png]]


# Sieb des Eratosthenes Java
---
```java 
private static ArrayList<Integer> getPrimes(int N){  
	boolean gestrichen[] = new boolean[N+1];  
	for (int i = 2 ; i <= gestrichen.length -1;i++){  
		gestrichen[i] = false;  
	}  

	for (int i = 2; i <= N; i++){  
		if(!gestrichen[i]){  
			//Set all multiples false if isn't set false  
			for (int j = i + i; j <= N; j+=i){  
				gestrichen[j] = true;  
			}  
		}  
	}  

	//Write the numbers in a list  
	ArrayList<Integer> list = new ArrayList();  
	for (int i = 1; i <= gestrichen.length-1; i++){  
		if(!gestrichen[i]){  
			list.add(i);  
		}  
	}  
	return list;  
} 

//Aufrufen
ArrayList<Integer> list = getPrimes(50);  
System.out.println(list);
```
# Primzahltester
---
```java
private static boolean isPrime(int n){  
    for (long i=2; i<=Math.sqrt(n); i++){  
        if (n%i == 0) {  
            return false;  
        }  
    }  
    return true;  
}
//Aufrufen
for(int u = 0; u < 10; u++){  
    System.out.print(u);  
    System.out.println(isPrime(u));  
}
```
