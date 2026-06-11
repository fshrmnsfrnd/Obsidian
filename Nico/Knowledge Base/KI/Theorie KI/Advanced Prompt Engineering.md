---
Fach:
Thema:
  - "[[KI]]"
---
>Beim Advanced Prompt Engineering gibt man mehr an, als nur eine einfache Frage. So kann man genauer steuern was und wie die KI antwortet.
>Häufig funktioniert das über JSON

**_Beispiel:_**
**Person:** 
- Beschreibe welche Rolle das LLM annehmen soll. 
- Beispiel: Du bist ein Expert der NASA
**Instruktion:** 
- Die Anweisung. 
- Sie sollte spezifisch sein. 
- Es soll nichts vergessen oder anders interpretiert werden können 
**Kontext:** 
- Weitere Information beschreiben den Kontext des Problems. 
- „Was ist der Grund für die Anweisung“. 
**Format:** 
- In welchem Format ausgegeben werden. 
- Beispiel: Python, Java, Word, Excel, PDF…
**Publikum:** 
- Welche Zielgruppe soll Ihr Ergebnis haben? 
**Ton:** 
- Welchen Ton möchten Sie treffen. Lässig, Vornehm, Geschäftsmäßig?
**Daten:** 
- Welche Daten sind notwendig für die Erstellung?

# Zero Shot Prompt
---
>Ein Zero Shot Prompt übergibt kein Beispiel an das LLM

```json
zero_shot_prompt=[ 
{"role": "user", 
 "content": "Eine Gitarre ist ein Musik Instrument. Eine Gitarre gibt es auch als E-Gitarre"}
]
```
# One Shot Prompt
---
>Ein One Shot Prompt übergibt mindestens ein Beispiel an das LLM

```json
One_shot_prompt=[ 
{"role": "user", 
 "content": "Eine Gitarre ist ein Musik Instrument. Eine Gitarre gibt es auch als E-Gitarre"}, 
{"role": "assistent", 
 "content": "Ich habe eine Gittare, die mir meine Tante geschenkt. Ich mag sie sehr gerne"}, 
{"role": "user", 
 "content": "Ein Beispiel für eine namhafte Gittare ist:"}
 ]
```
Beachte die unterschiedlichen Rollen
# Few Shot Prompt
---
>Ein Few-shot Prompt ist wie ein One-shot Prompt mit mehr als einem Beispiel.

**1. Prompt:**
```json
product_prompt = [
{"role": "user", 
 "content": "Erzeuge einen Namen und einen Slogan für einen Messenger."}
] 
outputs = pipe(product_prompt) 
product_description = outputs[0]["generated_text"] 
print(product_description) 
>>Bycs-Messenger, der Messenger der alle Wünsche erfüllt.
```

**2. Prompt:**
```json
sales_prompt = [
{"role": "user", 
 "content": f"Generate a very short sales pitch for the following product: '{product_description}'"}
] 
outputs = pipe(sales_prompt) 
sales_pitch = outputs[0]["generated_text"] 
print(sales_pitch) 
>>Der Bycs-Messenger kann folgendes
```
# Chain of thought Prompting
---
>Manchmal kann es passieren, dass Prompts logisch falsch verstanden werden. Dann macht es Sinn Prompts in Gedankenketten zu verwandeln.

```json
zero_shot_prompt=[
{"role": "user", 
 "content": „Die Cafeteria hat 23 Äpfel. Wenn Sie 20 für das Mittagessen verbrauchen und 6 Äpfel neu kaufen, wie viele Äpfel haben Sie dann? Denke Schritt für Schritt}'"}
]
```

![[Pasted image 20251017172231.png]]
# Output Verification
---
>Sollte man dringend tuen wenn man sein eigenes LLM betreibt

Um den Output zu kontrollieren kann man entweder Beispiele für die Ausgabe nutzen oder Fine-Tuning

**Strukturierter Output:**
Die meisten generativen Model verzichten auf eine strukturierte Ausgabe. Manche Anwendung erfordern es aber, dass die Ausgaben in einem bestimmten Forma wie JSON etc. erfolgen. 

**Gültige Aussage:**
Auch, wenn ein Model gezwungen wird ein Strukturierte Aussage zu erstellen, hat dieses noch einige Freiheiten. Beispielsweise sollte das Model keine drei Antworten erzeugen, wenn nur nach zwei möglichen Antworten gefragt ist. 

**Ethik:** 
Manchen generativen Modell haben keinen Richtlinien und generieren Ausgaben die weder sicher sind, noch ethische Aspekte berücksichtigen. 
(Obszönitäten, persönlich identifizierbare Informationen, voreingenommenheit, kulturelle Stereotypen, Rechte an Bild, Ton, Musik, etc.)  

**Accuracy:** 
Mit welcher Genauigkeit wurde meine Aufgabe beantwortet. Wie sachlich korrekt, kohärente ist die Ausgabe und ist diese freie von Halluzination?

