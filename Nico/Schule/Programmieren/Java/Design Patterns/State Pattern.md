---
Fach: "[[Programmieren]]"
Thema:
  - "[[Java]]"
  - "[[Design Patterns]]"
---
# Beispiel: Ampel
---
```java
public class Ampel {
    private AmpelState state;
    
    Ampel(){
       this.state = AmpelState.STOP;
    }
    
    Ampel(AmpelState state){
        setState(state);
    }
    
    public AmpelState getState(){
        return state;
    }
    
    public void setState(AmpelState state){
       this.state = state;
    }
    
    public void next(){
        if (state == AmpelState.STOP){
            this.state = AmpelState.NACH_STOP;
        }else if (state == AmpelState.NACH_STOP){
            this.state = AmpelState.FAHREN;
        }else if (state == AmpelState.FAHREN){
            this.state = AmpelState.VOR_STOP;
        }else if (state == AmpelState.VOR_STOP){
            this.state = AmpelState.STOP;
        }
    }
    
    public void ausschalten(){
        this.state = AmpelState.AUS;
    }  
    
    public void showState(){
        state.showState();
    }
}
```

```Java
public enum AmpelState {
    AUS("AUS",false,false,false),
    STOP("STOP",true,false,false),
    NACH_STOP("NACH STOP",true,true,false),
    FAHREN("FAHREN",false,false,true),
    VOR_STOP("VOR STOP",false,true,false);
    
    public final String stateName;
    public final boolean red;
    public final boolean yellow;
    public final boolean green;
    
    AmpelState(String name,boolean red, boolean yellow, boolean green){
        this.stateName = name;
        this.red = red;
        this.yellow = yellow;
        this.green = green;
    }
    
    public void showState(){
        System.out.println("Status: " + this.stateName);
        System.out.println("-------------------------");
        System.out.println("Red:\t" + this.red + "\t" + (this.red == true? "(X)":"(_)"));
        System.out.println("Yellow:\t" + this.yellow + "\t" + (this.yellow == true? "(X)":"(_)"));
        System.out.println("Green:\t" + this.green + "\t" + (this.green == true? "(X)":"(_)"));
        System.out.println("");
    }
}
```