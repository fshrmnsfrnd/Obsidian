---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
# Wahrheitstabelle

| $t^m$ |       |       |       | \|  | $t^{m+1}$                             |                                       |                                       |                                       |
| ----- | ----- | ----- | ----- | --- | ------------------------------------- | ------------------------------------- | ------------------------------------- | ------------------------------------- |
| $q_d$ | $q_c$ | $q_b$ | $q_a$ | \|  | $q_d$                                 | $q_c$                                 | $q_b$                                 | $q_a$                                 |
| 0     | 0     | 0     | 0     | \|  | 0                                     | 0                                     | 0                                     | 1                                     |
| 0     | 0     | 0     | 1     | \|  | 0                                     | 0                                     | 1                                     | 0                                     |
| 0     | 0     | 1     | 0     | \|  | 0                                     | 0                                     | 1                                     | 1                                     |
| 0     | 0     | 1     | 1     | \|  | 0                                     | 1                                     | 0                                     | 0                                     |
| 0     | 1     | 0     | 0     | \|  | 0                                     | 1                                     | 0                                     | 1                                     |
| 0     | 1     | 0     | 1     | \|  | 0                                     | 1                                     | 1                                     | 0                                     |
| 0     | 1     | 1     | 0     | \|  | 0                                     | 1                                     | 1                                     | 1                                     |
| 0     | 1     | 1     | 1     | \|  | 1                                     | 0                                     | 0                                     | 0                                     |
| 1     | 0     | 0     | 0     | \|  | 1                                     | 0                                     | 0                                     | 1                                     |
| 1     | 0     | 0     | 1     | \|  | <span style="color: yellow;">0</span> | <span style="color: yellow;">0</span> | <span style="color: yellow;">0</span> | <span style="color: yellow;">0</span> |
| 0     | 0     | 0     | 0     | \|  | 0                                     | 0                                     | 0                                     | 1                                     |

**Taktunabhängig:**
=> $R = (\overline{q_a} \land q_b \land \overline{q_c} \land q_d)$
=> $\bar{R} = \overline{(\overline{q_a} \land q_b \land \overline{q_c} \land q_d)}$
