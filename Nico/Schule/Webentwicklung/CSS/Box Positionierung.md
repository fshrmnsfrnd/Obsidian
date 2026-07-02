---
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
`position: [absolute, relative, fixed, static, sticky]`

Mit `top`, `right`, `bottom`, `left` kann die genaue Position angegeben werden – diese wirken sich aber **nur** bei positionierten Elementen aus (also nicht bei `static`).

| Wert       | Beschreibung                                                                                                   |
| ---------- | -------------------------------------------------------------------------------------------------------------- |
| `static`   | Standardwert. Element folgt dem normalen Dokumentenfluss. `top`/`left` etc. haben **keine** Wirkung.          |
| `relative` | Element bleibt im Dokumentenfluss, kann aber relativ zur **eigenen Ursprungsposition** verschoben werden.     |
| `absolute` | Element wird aus dem Dokumentenfluss herausgenommen. Positionierung relativ zum nächsten positionierten Vorfahren. |
| `fixed`    | Wie `absolute`, aber relativ zum **Viewport**. Bleibt beim Scrollen an derselben Stelle.                      |
| `sticky`   | Verhält sich wie `relative`, bis ein Scroll-Schwellenwert erreicht wird – dann wie `fixed`.                   |

> [!NOTE] „Positionierter Vorfahre" bedeutet: das nächste Elternelement, das **nicht** `position: static` hat.
# Vergleich im Überblick
---

| Wert       | Im Dokumentenfluss? | Bezugspunkt                      | Scrollt mit? |
| ---------- | ------------------- | -------------------------------- | ------------ |
| `static`   | ja                  | –                                | ja           |
| `relative` | ja                  | Eigene Ursprungsposition         | ja           |
| `absolute` | nein                | Nächster positionierter Vorfahre | ja           |
| `fixed`    | nein                | Viewport                         | nein         |
| `sticky`   | ja (zunächst)       | Scrollcontainer                  | teilweise    |
# Beispiele
---
## `relative`
```css
.box {
    position: relative;
    top: 20px;   /* 20px nach unten verschoben */
    left: 10px;  /* 10px nach rechts verschoben */
}
```
> [!NOTE] Der ursprüngliche Platz im Layout bleibt reserviert – andere Elemente rücken **nicht** nach.

## `absolute`
```css
.parent {
    position: relative; /* Bezugspunkt für das Child */
}

.child {
    position: absolute;
    top: 0;
    right: 0; /* oben rechts im Parent */
}
```
> [!WARNING] Ohne positionierten Parent gilt der `<body>` als Bezugspunkt.

## `fixed`
```css
.navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
}
```

## `sticky`
```css
.header {
    position: sticky;
    top: 0; /* klebt an dieser Position, sobald der Scroll-Schwellenwert erreicht wird */
}
```
> [!NOTE] `sticky` benötigt zwingend eine Angabe wie `top`, `bottom` etc., sonst verhält es sich wie `relative`.

# z-index
---
Positionierte Elemente (alle außer `static`) können mit `z-index` gestapelt werden.

```css
.overlay {
    position: absolute;
    z-index: 10; /* liegt über Elementen mit niedrigerem z-index */
}
```
> [!NOTE] `z-index` funktioniert **nur** bei positionierten Elementen.