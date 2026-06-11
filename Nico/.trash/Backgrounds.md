---
Fach: "[[INTL]]"
tags:
Thema:
  - "[[CSS]]"
---
# Properties
---

| Property                 | Description                                |
| ------------------------ | ------------------------------------------ |
| `background:`            | _(Shorthand)_                              |
| `background-color:`      | See: [[Colors]]                            |
| `background-image:`      | url(...)                                   |
| `background-position:`   | left/center/right<br/>top/center/bottom    |
| `background-size:`       | cover X Y                                  |
| `background-clip:`       | border-box<br/>padding-box<br/>content-box |
| `background-repeat:`     | no-repeat<br/>repeat-x<br/>repeat-y        |
| `background-attachment:` | scroll/fixed/local                         |
# Shorthand
---

|               | color  | image        | positionX | positionY |     | size           | repeat      | attachment |
| ------------- | ------ | ------------ | --------- | --------- | --- | -------------- | ----------- | ---------- |
| `background:` | `#ff0` | `url(a.jpg)` | `left`    | `top`     | `/` | `100px` `auto` | `no-repeat` | `fixed;`   |
| `background:` | `#abc` | `url(b.png)` | `center`  | `center`  | `/` | `cover`        | `repeat-x`  | `local;`   |
|               | color  | image        | posX      | posY      |     | size           | repeat      | attach..   |
# Examples
---
```css {.wrap}
background: url(img_man.jpg) no-repeat center;

background:
  url(img_flwr.gif) right bottom no-repeat,
  url(paper.gif) left top repeat;

background: rgb(2, 0, 36);

background: linear-gradient(
  90deg,
  rgba(2, 0, 36, 1) 0%,
  rgba(13, 232, 230, 1) 35%,
  rgba(0, 212, 255, 1) 100%
);
```
