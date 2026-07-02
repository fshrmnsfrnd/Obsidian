---
Fach:
Thema:
  - "[[KI]]"
---
>Um der KI die menschliche Sprache verständlich zu machen nutzt man Tokens

**Word Tokens:**
ganze Wörter werden als Token erfasst. Diese Methode wird immer seltener benutzt, da das LLM schlecht neue Wörter lernen kann

**Subword Tokens:**
Diese Variante beinhaltet sowohl ganze als auch Teilwörter. Durch die Zusammensetzung verschiedener Tokens können so später auch neue Wörter gelernt werden

**Character Tokens:**
Diese Variante nimmt jeden Buchstaben einzeln als Token. Dadurch können ebenfalls neue Wörter gut erlernt werden. Allerdings wird das spätere generieren einer Text Ausgabe viel schwieriger, da jeder Buchstabe einzeln gesetzt werden muss.

**Byte Tokens:**
Bei dieser Variante wird jeder Buchstabe als eine Byte Darstellung, also eine Kombination aus 010010110…. dargestellt. Im Vergleich dazu, ist der Charakter Token eine Ganzzahl „353254“.
# Tokenizer
---
- Der **Tokenizer** wandelt **Text in Tokens** um (vor dem Training oder der Eingabe).
- Beim Ausgeben wandelt er Tokens wieder in **Text** zurück.
- Er sorgt dafür, dass das Modell mit Zahlen statt Text arbeiten kann.