---
Fach:
Thema:
  - "[[KI]]"
aliases:
  - LLM
  - LLMs
---
# Arten von LLMs
## Generative Modelle
>Das bedeutet, dass aus Eingaben mittels generativer Modelle und gespeicherter Lerndaten neue Ergebnisse/Ausgaben wie Texte, Sprachaussagen, Vertonungen, Bilder oder Videos erzeugen. Generative KI-Modelle erlernen Muster und Strukturen vorgängig eingegebener Trainingsdaten und generieren daraus neue Daten mit ähnlichen Eigenschaften

Beispiele:
- Llama
- GPT
- Gemini
- Claude
## Repräsentative Modelle
>Repräsentative Modelle zielen darauf ab, Daten zu klassifizieren oder zu kategorisieren. Sie lernen Muster und Merkmale, um Eingabedaten in vordefinierte Kategorien einzuordnen. 

Beispiele: 
- Bildklassifikation: Ein Modell, das Katzen von Hunden unterscheidet 
- Spam-Filter in E-Mail-Programmen 
- Gesichtserkennung 
- Sentiment-Analyse von Texten (positiv/negativ)

# Prompting
## Regeln für einen guten Prompt
**Spezifisch:**
Beschreibe was du erreichen möchtest. 
Beispiel: „Schreibe eine Beschreibung für ein Produkt“ 
oder besser 
„Schreibe eine Beschreibung für ein Produkt in weniger als zwei Sätzen“ 

**Halluzinationen:** 
LLMs können falsche Informationen erzeugen. Dies nenn man Hallucination. Um dies zu reduzieren, können wir dem LLM sagen 
„Erzeuge nur eine Antwort, wenn du das Ergebnis weißt, ansonsten sage, dass du es nicht weist. 

**Sortieren:** 
Beginnen oder Enden Sie mit der Anweisung. 
Vor allem bei langen Prompts können Informationen in der Mitte vergessen werden. LLMs neigen dazu sich auf Informationen am Anfang (primacy effect) oder am Ende (recency effect) zu fokussieren.
## [[Advanced Prompt Engineering]]

# Funktionsweise
[[Aufbau LLM.canvas]]
![[Pasted image 20251201175823.png]]