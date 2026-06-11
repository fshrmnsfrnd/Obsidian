---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Java]]"
---
# Exceptions abfangen
---
```java
try{
	int ergebnis = 1 / 0;
}catch(Exception e){
	System.err.println(e.getLocalizedMessage());
}finally { 
	System.out.println("Programm fertig."); 
}
```
Wenn im `try` Block ein Fehler auftritt, wird der Code abgebrochen und die Exception als `e` an den `catch` Block übergeben und dort wird der Code weiter ausgeführt.
Der `finally` Block wird ohne Ausnahme immer ausgeführt
# Verschiedene Arten von Exceptions
---
Es gibt viele verschiedene [[Klassen in Java|Klassen in Java]] von Exceptions. 
Es können im `catch` Block verschiedene Arten von Exceptions abgefangen werden. Die letzte `catch` Anweisung sollte immer `Exception` abfangen um aller nicht vorher genannten Fehlertypen abzufangen.
```java
try { 
	int ergebnis = 1 / input;
} catch (ArithmeticException e1) { 
	System.err.println("Division durch Null!"); 
} catch (InputMismatchException e2) { 
	System.err.println("Das ist keine ganze Zahl."); 
} catch (Exception e3) { 
	System.out.println("Fehler: " + e3.getLocalizedMessage());
}
```

Es können auch verschiedene Fehler in eine `catch` Block abgefangen werden
```java
try { 
	int ergebnis = 1 / input;
} catch (ArithmeticException | InputMismatchException e1) { 
	System.out.println("Fehler: " + e3.getLocalizedMessage());
}
```
# Try mit Ressourcen
---
```java
try(PrintWriter ressource = new PrintWriter("D:/Ausgabedatei.txt")){
	out.println("Test2"); 
} catch (FileNotFoundException ex) {
	// ... Fehlermeldung ...
}
```

> [!NOTE] Das geht mit allen Klassen die `AutoClosable` implementieren

# Beispiel
---
```java
private static Scanner scan = new Scanner(System.in); // Scanner initialisieren
    
    public static int einlesen() { //Funktion zum Einlesen einer Ganzzahl
        int zahl = 0;
        try {
            zahl = Integer.parseInt(scan.nextLine()); // Einlesen
        } catch (NumberFormatException e) {
            System.out.println("Keine gültige Zahl " + e.getLocalizedMessage());
            zahl = einlesen(); //Funktion neu aufrufen
        }
        return zahl;
    }

    public static void main(String[] args) {
        System.out.println("Dividend:");
        int dividend = einlesen();
        System.out.println("Divisor:");
        int divisor = einlesen();
        
        int ergebnis = 0;
        int rest = 0;
        
        try{
            ergebnis = dividend / divisor; //Berechnen
            rest = dividend % divisor; //Rest berechnen
            //Das Ergebnis wird nur ausgegeben wenn kein Fehler geworfen wurde
            System.out.println("Erg: " + ergebnis + " Rest: " + rest);
        }catch(Exception e){
            System.out.println("Fehler bei der Rechenoperation"  + e.getLocalizedMessage());
        }
    }
```
# Fehler werfen
---
In Klassen ist es häufig sinnvoller Fehler zu werfen als sie zu behandeln:
```java
public class MyClass{
	public static int myFunc(int n){
		if(n >= 10){
			throw new IndexOutOfBoundsException("Zahl zu hoch!");
		}
		return n;
	}
}

void main(){
	try{
		MyClass.myFunc(11);
	}catch(IndexOutOfBoundsException e){
		System.err.println(e.getMessage())
	}
}
```
# Eigene Fehlerklassen
---
Für eine eigene Fehlerklasse muss man von der Klasse `Exception` oder einer ihrer Unterklassen erben.
```java
public class CheckedLengthException extends Exception { 
	public CheckedLengthException() { 
		super("Der Text ist zu lang!");
	}
}
```

# Eigene Exceptions
---
## Checked Exceptions
>Checked Exceptions erben von `Exceptions`. 
>Wird hier die [[Schule/Programmieren/Java/Basics/Fehlerbehandlung|Fehlerbehandlung]] weggelassen kann der Code nicht compiliert werden
### Eigene Fehlerklasse
```java
public class CheckedLengthException extends Exception { 
	public CheckedLengthException() { 
		super("Der Text ist zu lang!"); 
	} 
}
```
### Erzeugen eines Exception Objektes (Werfen eines Fehlers)
> [!IMPORTANT] Wo Checked Exceptions geworfen werden muss `<method> throws <MyException>` dabei sein
```java
public void check(String input, int maxLength) throws CheckedLengthException { 
	if (input.length > maxLength) { 
		throw new CheckedLengthException(); 
	} 
}
```
## Unchecked Exceptions
> Fehlerklassen, die von der Klasse `RuntimeException erben`
> Hier kann der Code auch kompiliert werden, wenn es keine Fehlerbehandlung gibt

```java
public class UnCheckedLengthException extends RuntimeException { 
	public UnCheckedLengthException() { 
		super("Der Text ist zu lang!"); 
	} 
}
```
