---
Fach:
tags:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
## Properties

| Property          | Description     |
| ----------------- | --------------- |
| `font-family:`    | \<font> <fontN> |
| `font-size:`      | \<size>         |
| `letter-spacing:` | \<size>         |
| `line-height:`    | \<number>       |

| `font-weight:` | \<number> / bold / normal | | `font-style:` | italic / normal | | `text-decoration:` | underline /
none |

| `text-align:` | left / right
center / justify | | `text-transform:` | capitalize / uppercase / lowercase | {.left-text}

### Shorthand

|         | style    | weight | size (required) |     | line-height | family            |
| ------- | -------- | ------ | --------------- | --- | ----------- | ----------------- |
| `font:` | `italic` | `400`  | `14px`          | `/` | `1.5`       | `sans-serif`      |
|         | style    | weight | size (required) |     | line-height | family (required) |

## Example
```css
font-family: Arial, sans-serif;
font-size: 12pt;
letter-spacing: 0.02em;
```

## Case 
```css
/* Hello */
text-transform: capitalize;

/* HELLO */
text-transform: uppercase;

/* hello */
text-transform: lowercase;
```

## @font-face
```css
@font-face {
  font-family: 'Glegoo';
  src: url('../Glegoo.woff');
}
```
