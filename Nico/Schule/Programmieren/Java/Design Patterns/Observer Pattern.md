---
Thema:
  - "[[Java]]"
  - "[[Design Patterns]]"
---
Nicht so kompliziert wie Lingo es erklärt:
Ein Subject hat Daten und eine Liste welche Objekte (Observer) bescheid bekommen wollen, wenn sich die Daten ändern. Dann geht er die Observerliste durch und sagt allen Observern, dass es ein Update gab. Deswegen ein Interface für Observer, damit überall die Methode `.update()` verfügbar ist. Was die Observer dann damit machen ist ihr Bier.
In der reinen Lehre werden in `.update()` keine Daten übergeben, davon kann aber abgewichen werden.

![[Pasted image 20260305105421.png]]

# Beispiel Liste mit Anzeige
---
**Subject**
```java
public interface Subject {  
    void registerObserver(Observer o);  
    void unregisterObserver(Observer o);  
    void notifyObservers();  
}
```

**Concrete Subject**
```java
import java.util.ArrayList;  
  
public class InputSubject implements Subject {  
    private ArrayList<Observer> observers = new ArrayList<>();  
    private ArrayList<String> inputs = new ArrayList<>();  
  
    @Override  
    public void registerObserver(Observer o) {observers.add(o);}  
    
    @Override  
    public void unregisterObserver(Observer o) {observers.remove(o);}  
    
    @Override  
    public void notifyObservers() {  
        for (Observer o : observers) {  
            o.update();  
        }  
    } 
    
    public ArrayList<String> getInputs() {return inputs;}  
    
    public void addInput(String input) {  
        inputs.add(input);  
        this.notifyObservers();  
    } 
}
```

**Observer**
```java
public interface Observer {  
    void update();  
}
```

**Concrete Observer**
```java
public class ListTextObserver implements Observer {  
    TextArea outputField;  
    InputSubject subject;  
  
    public ListTextObserver(TextArea outputField, InputSubject subject) {  
        this.outputField = outputField;  
        this.subject = subject;  
    }  
  
    @Override  
    public void update() {  
        outputField.clear();  
        for(String input: subject.getInputs()){  
            outputField.appendText(input + "\n");  
        }  
    }  
}
```

**Main**
```java
InputSubject subject;  
  
public void initialize() {  
    subject = new InputSubject();  
    subject.registerObserver(new LatestTextObserver(textFieldLatestText, subject));  
    subject.registerObserver(new ListTextObserver(textFieldList, subject));  
}  
  
@FXML  
protected void onSaveButtonClick() {  
    subject.addInput(txtInput.getText());  
}
```