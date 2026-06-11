---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---
>Link Aggregation bedeutet, dass mehrere Leitungen **parallel** geschaltet sind.

**Vorteil:**
- Mehrere Leitungen sind meist billiger als eine große

**Beispiel**
Aus 2 parallelen 1Gb/s Leitungen wird eine große 2Gb/s Leitung.

Link Aggregation (IEEE 802.3ad), auch als Trunking geläufig, ist eine Spielart von Spanning Tree, mit der man mehrere Ports parallel schaltet, um den Durchsatz zu vervielfachen. Zwei oder vier Twisted-Pair-Gigabit-Ports als Backbone zwischen Switches oder zur Anbindung eines schnellen Servers sind nämlich immer noch billiger als ein 10-Giga-bit-Glasfaser-Link. Zwar gehen dann nur zwei oder vier GBit/s statt zehn herüber, doch das kann in vielen Fällen genügen. Trunking funktioniert nur bei Ports mit gleicher Datenrate und im Vollduplexbetrieb. Die Konfiguration funktioniert auch automatisch, wenn beide Seiten das Link Aggregation Control Protocol (LACP) beherrschen. Es arbeitet ähnlich wie STP