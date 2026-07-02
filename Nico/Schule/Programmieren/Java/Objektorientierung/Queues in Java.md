---
Thema:
  - "[[Java]]"
---
# Single Linked List
![[Pasted image 20251210124941.png]]
## Objekt hinzufügen
![[Pasted image 20251210125030.png]]
## Objekt entfernen
![[Pasted image 20251210125146.png]]
# Double Linked List
![[Pasted image 20251210125236.png]]
# Code
---
## Single Linked List
```java
import java.util.NoSuchElementException;  
  
public class IntegerList{
    private final IntegerNode head;
    private final IntegerNode tail;

    public IntegerList(){
        tail = new IntegerNode(null);
        head = new IntegerNode(null);

        tail.setNext(head);
        head.setNext(tail);
    }

    protected IntegerNode getHead(){return head;}
    protected IntegerNode getTail(){return tail;}
    public boolean isEmpty(){return head.getNext() == tail;}

    public Integer pop(){
        if (this.isEmpty()){
            throw new NoSuchElementException("IntegerList empty, pop() not possible");
        }
        IntegerNode firstNode = head.getNext();
        IntegerNode secondNode = firstNode.getNext();
        head.setNext(secondNode);
        if (head.getNext() == tail){
            tail.setNext(head);
        }
        return firstNode.getObject();
    }

    public Integer peek(){
        if (this.isEmpty()){
            throw new NoSuchElementException("IntegerList empty, peek() not possible");
        }
        return head.getNext().getObject();
    }

    @Override
    public String toString(){
        StringBuilder sb = new StringBuilder("[");
        IntegerNode pointer = head.getNext();
        while (pointer != tail){
            sb.append(pointer.getObject());
            pointer = pointer.getNext();
            if (pointer != tail){
                sb.append("; ");
            }
        }
        sb.append("]");
        return sb.toString();
    }
}
  
public class IntegerNode{
    private final Integer object;
    private IntegerNode next;

    public IntegerNode(Integer object){
        this.object = object;
        this.next = null;
    }

    public Integer getObject(){return object;}
    public IntegerNode getNext(){return next;}
    public void setNext(IntegerNode next){this.next = next;}
}
```