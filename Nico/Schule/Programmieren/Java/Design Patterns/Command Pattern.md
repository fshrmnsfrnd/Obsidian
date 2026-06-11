---
Fach: "[[Programmieren]]"
Thema:
  - "[[Design Patterns]]"
  - "[[Java]]"
---
![[Pasted image 20260305111132.png]]

**Command**: deklariert eine Schnittstelle zum Ausführen einer Methode.
**Concrete Command**: Erbt von `Command` und implementiert `.execute()`. Verpackt eine Funktion, die eigene Logik enthalten kann und/oder etwas der Receiver Klasse ausführt.
**Client**: die Anwendung (Main)
**Invoker**: Verwaltet die Concrete Commands. Hier können `.undo()` usw. implementiert werden
**Receiver**: Jede Klasse kann ein Receiver sein. Hier werden die Receiver Methoden von einem Concrete Command verpackt
# Beispiel
---
**Command**
```java
public interface Command{
	public void execute();
}
```
**Receiver**
```java
public class Receiver{
	public void doSomething(String state){
		System.out.println("State: " + state);
	}
}
```
**Concrete Command**
```java
public class ConcreteCommand implements Command{
	private Receiver receiver;
	private String state;
	
	public ConcreteCommand(Receiver receiver){
		this.receiver = receiver;
	}
	
	@Override
	public void execute(){
		receiver.doSomething(state);
	}
	
	public void setState(String state){
		this.state = state;
	}
}
```
**Invoker**
```java
public class Invoker{
	private Command command;
	
	public void setCommand(Command command){
		this.command = command;
	}
	
	public void executeCommand(){
		command.execute();
	}
}
```
**Client (Main)**
```java
public class Main{
	public static void main(String[] args){
		Receiver receiver = new Receiver();
		String state1 = "STATE_ON";
		String state2 = "STATE_OFF";
		
		ConcreteCommand concreteCommand1 = new ConcreteCommand(receiver);
		concreteCommand1.setState(state1);
		
		ConcreteCommand concreteCommand2 = new ConcreteCommand(receiver);
		concreteCommand2.setState(State2);
		
		Invoker invoker1 = new Invoker();
		invoker1.setCommand(concreteCommand1);
		Invoker invoker2 = new Invoker();
		invoker2.setCommand(concreteCommand2);
		
		invoker1.executeCommand(); // Output: State: STATE_ON
		invoker2.executeCommand(); // Output: State: State_OFF
	}
}
```