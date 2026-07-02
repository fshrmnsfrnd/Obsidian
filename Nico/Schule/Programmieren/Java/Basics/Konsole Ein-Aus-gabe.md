---
Thema:
  - "[[Java]]"
---
# Ausgabe
```java
String a = "!";
System.out.println("Hello World" + a);
```
# Eingabe
Package einbinden:
`import java.util.Scanner;`
### Beispiel
```java
import java.util.Scanner;

public static void main(String args[]){
	Scanner scan = new Scanner(System.in);
	int eingabe = scan.nextInt();
}
```
>Der Java Scanner ließt Typsicher mit den Methoden nextInt(), nextBoolean() usw. eingegeben

