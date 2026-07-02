---
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# Shorthand
|              | name     | duration | timing-function | delay   | count      | direction           | fill-mode | play-state |
| ------------ | -------- | -------- | --------------- | ------- | ---------- | ------------------- | --------- | ---------- |
| `animation:` | `bounce` | `300ms`  | `linear`        | `100ms` | `infinite` | `alternate-reverse` | `both`    | `reverse`  |
|              | name     | duration | timing-function | delay   | count      | direction           | fill-mode | play-state |
# Properties
| Property                     | Value                                                  |
| ---------------------------- | ------------------------------------------------------ |
| `animation:`                 | _(shorthand)_                                          |
| `animation-name:`            | \<name>                                                |
| `animation-duration:`        | \<time>ms                                              |
| `animation-timing-function:` | ease / linear / ease-in / ease-out / ease-in-out       |
| `animation-delay:`           | \<time>ms                                              |
| `animation-iteration-count:` | infinite / \<number>                                   |
| `animation-direction:`       | normal / reverse / alternate / alternate-reverse       |
| `animation-fill-mode:`       | none / forwards / backwards / both / initial / inherit |
| `animation-play-state:`      | normal / reverse / alternate / alternate-reverse       |
# Example 
```css
/* @keyframes duration | timing-function | delay |
   iteration-count | direction | fill-mode | play-state | name */
animation: 3s ease-in 1s 2 reverse both paused slidein;

/* @keyframes duration | timing-function | delay | name */
animation: 3s linear 1s slidein;

/* @keyframes duration | name */
animation: 3s slidein;

animation: 4s linear 0s infinite alternate move_eye;
animation: bounce 300ms linear 0s infinite normal;
animation: bounce 300ms linear infinite;
animation: bounce 300ms linear infinite alternate-reverse;
animation: bounce 300ms linear 2s infinite alternate-reverse forwards normal;
```
# [[JavaScript]] Event
```js
.one('webkitAnimationEnd oanimationend msAnimationEnd animationend')
```
