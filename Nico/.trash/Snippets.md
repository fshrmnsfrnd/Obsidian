---
Fach: "[[DB]]"
---
# Text zwischen 2 Zeichen
---
```sql
SET Name = SUBSTRING(tweet,
                     LOCATE("@", tweet, 1)+1,
                     LOCATE("@", tweet, LOCATE("@", tweet, 1)+1) - LOCATE("@", tweet, 1)-1);
```
