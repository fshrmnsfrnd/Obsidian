---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Java]]"
---
# IF
---
```java
if(true){
	//code
}else if(true){
	//code
}else{
	//code
}
```
# Switch Case
---
```java
switch (state){  
    case RED -> state = AmpelState.GREEN;  
    case GREEN -> state = AmpelState.RED;   
    default -> state = AmpelState.RED;  
}
```
oder
```java
switch (state){  
    case RED -> {
	    state = AmpelState.GREEN;
	}  
    case GREEN -> {
	    state = AmpelState.RED;
	}   
    default -> {
	    state = AmpelState.RED;
	}  
}
```
