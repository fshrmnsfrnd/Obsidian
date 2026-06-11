---
Fach:
tags:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
## !important
```css
.post-title {
  color: blue !important;
}
```
Overrides all previous styling rules.
## Scrollbar smooth
```css
html {
  scroll-behavior: smooth;
}
```
## container queries(size)
```css
.element-wrap {
  container: element / inline-size;
}
@container element (min-inline-size: 300px) {
  .element {
    display: flex;
    gap: 1rem;
  }
}
```
## container qeries(style)
```css
.container {
  --variant: 1;

  &.variant2 {
    --variant: 2;
  }
}

@container style(--variant: 1) {
  button {
  } /* You can't style .container, but can select inside it */
  .other-things {
  }
}

@container style(--variant: 2) {
  button {
  }
  .whatever {
  }
}
```
## container units
- The units are cqw (“container query width”),
- cqh (“container query height”),
- cqi (“container query inline”),
- cqb (“container query block”),
- cqmin (smaller of cqi and cqb),
- and cqmax (larger of cqi and cqb)

```css
.card {
  padding: 5cqi;
  font-size: 4cqi;
  border: 1cqi solid brown;
  height: 100%;
}

h2 {
  font-size: 10cqi;
  margin-block: 0 3cqi;
}
```
## the :has() pseudo selector
```css
figure:has(figcaption) {
  border: 1px solid black;
  padding: 0.5rem;
}
```
## nesting
```css
.cards {
  .card {
    & .card-description {
      color: blue;
    }
    & .card-title {
      color: red;
    }
  }
}
```
## scoping
```css
@scope {
  :scope {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
    padding: 1rem;
    border: 1px solid black;
  }
  .card {
    padding: 1rem;
    border: 1px solid black;
    background: lightgray;
    h2 {
      margin: 0 0 1rem 0;
    }
  }
}
```
## cascade layers
```css
/* Specify the order to apply styles in cascade */
@layer legacyCard, newCard;

/* Imagine you have a lot of styles */
@layer newCard {
  .card {
    background-color: red;
  }
}
@layer legacyCard {
  .card {
    background-color: green;
  }
}
```
## logical properties
```css
button {
  background-color: #4caf50;
  border: none;
  color: white;
  padding: 0.5rem 1.5rem;
  text-decoration: none;
  font: inherit;
  border-radius: 4px;
  .icon {
    position: relative;
    top: 0.125em;
    fill: white;
    width: 1em;
    aspect-ratio: 1;
    margin-inline-end: 0.25rem;
  }
}
```
## p3 colors
```html
<div class="container">
  <div class="swatch">
    <style contenteditable>
      @scope {
        :scope {
          background-color: color(display-p3 1 0.5 0);
        }
      }
    </style>
  </div>
  <div class="swatch">
    <style contenteditable>
      @scope {
        :scope {
          background-color: oklch(61.88% 0.286 342.4);
        }
      }
    </style>
  </div>
  <div class="swatch">
    <style contenteditable>
      @scope {
        :scope {
          background-color: oklab(0.73 0.15 0.16);
        }
      }
    </style>
  </div>

  <div class="swatch">
    <style contenteditable>
      @scope {
        :scope {
          background-image: linear-gradient(to right in oklch, red, blue);
        }
      }
    </style>
  </div>

  <div class="swatch">
    <style contenteditable>
      @scope {
        :scope {
          background-image: linear-gradient(to right in oklab, red, blue);
        }
      }
    </style>
  </div>

  <div class="swatch">
    <style contenteditable>
      @scope {
        :scope {
          background-image: linear-gradient(to right in srgb, red, blue);
        }
      }
    </style>
  </div>
</div>
```
## color mixing
```css
.swatch {
  color: white;
  width: 100px;
  aspect-ratio: 1;
  display: grid;
  place-items: center;
  text-align: center;

  &:nth-child(1) {
    background-color: var(--bg);
  }
  &:nth-child(2) {
    background-color: color-mix(in oklch, var(--bg), black 30%);
  }
  &:nth-child(3) {
    background-color: color-mix(in oklch, var(--bg), white 30%);
  }
}
```
## margin trim
```css
.container {
  /* prevent "extra" margin at the end of the element */
  margin-trim: block-end;

  /* an element like this might be the culprit, but it could be anything */
  > p {
    margin-block-end: 1rem;
  }
}
```
## text wrapping
```css
.balance {
  text-wrap: balance;
}
.pretty {
  text-wrap: pretty;
}

html {
  font-family: system-ui, sans-serif;
}

main {
  max-inline-size: 60ch;
  margin-inline: auto;
}
```