---
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
Flexboxen sind für **eindimensionale** Layouts, also Reihe oder Spalte.
Der Container an dem `display: flex` gesetzt wird, ist der **Flexcontainer**, die direkten Unterelemente die **Flex Children**.
# Simple example
```css
.container {
	/*Flex Container*/
	display: flex;
}
```

```css
.container > div {
	/*Flex Child*/
	flex: 1 1 auto;
}
```
# Container
---
## Container Art
```css
display: flex;
display: inline-flex;
```
## Ausrichtung
In welcher Reihenfolge und in welcher Richtung die Elemente angeordnet werden
```css
flex-direction: row; /* left-right - default */
flex-direction: row-reverse; /* right-left */
flex-direction: column; /* top-bottom */
flex-direction: column-reverse; /* bottom-top */
```
## Wrap
```css
flex-wrap: nowrap; /* one-line */
flex-wrap: wrap; /* multi-line */
```
## Ausrichtung **senkrecht zur flex-direction**
```css
align-items: flex-start; /* vertical-align to top */
align-items: flex-end;   /* vertical-align to bottom */
align-items: center;     /* vertical-align to center */
align-items: stretch;    /* same height on all (default) */
```
## Ausrichtung **mit der flex-direction**
```css
justify-content: flex-start;    /* [xxx        ] */
justify-content: center;        /* [    xxx    ] */
justify-content: flex-end;      /* [        xxx] */
justify-content: space-between; /* [x    x    x] */
justify-content: space-around;  /* [ x   x   x ] */
justify-content: space-evenly;  /* [  x  x  x  ] */
```
# Children (Flex Items)
---
```css
/* This: */
flex: 1 0 auto; /*grow shrink basis*/

/* Is equivalent to this: */
flex-grow: 1; /*Breite relativ zu den anderen Elementen, wenn die Basisbreite vergrößert wird*/
flex-shrink: 0;/*Breite relativ zu den anderen Elementen fest, wenn die Basisbreite verkleinert wird*/
flex-basis: auto; /*Basisbreite eines Flex-Items*/
```

```css
order: 1; /*Position (-1 = Anfang)*/
```

```css
align-self: flex-start; /* left */
margin-left: auto; /* right */
```
# CSS Flexbox Tricks
---
## Vertical center
```css
.container {
  display: flex;
}

.container > div {
  width: 100px;
  height: 100px;
  margin: auto;
}
```
## Reordering
```css
.container > .top {
  order: 1;
}

.container > .bottom {
  order: 2;
}
```
## Mobile layout
```css
.container {
  display: flex;
  flex-direction: column;
}

.container > .top {
  flex: 0 0 100px;
}

.container > .content {
  flex: 1 0 auto;
}
```
A fixed-height top bar and a dynamic-height content area.
## Table-like 
```css
.container {
  display: flex;
}

/* the 'px' values here are just suggested percentages */
.container > .checkbox {
  flex: 1 0 20px;
}
.container > .subject {
  flex: 1 0 400px;
}
.container > .date {
  flex: 1 0 120px;
}
```
This creates columns that have different widths, but size accordingly according to the circumstances.