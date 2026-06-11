---
Fach:
Thema:
  - "[[KI]]"
---
>Bei Lang Chain geht es um den Kontext des ganzen Promptes. Also z.B. bei einem Chatbot den vorhergegangenen Gesprächsverlauf.

# Arten von Conversation Buffers
## Conversation Buffer
Hier wird der gesamte Verlauf wieder mit in die neue Anfrage gegeben
## Windowed Conversation Buffer
Es wird nur eine gewisse Länge des Verlaufs gebuffert.
## Conversation Summary
Es wird eine Zusammenfassung des gesamten Verlaufs gebuffert.
Hier ist das Ergebnis stark abhängig von der Qualität der Zusammenfassung.
# Agents
LLMs können Tools nutzen (z.B. Taschenrechner)
## ReAct - Reasoning and Acting
### Instruktion
Löse das Problem aus dem Prompt
### ReAct
- Denken (Thought)
- Aktion (Action)
- Beobachtung (Observe)
### Beschreibung
Eine Beobachtung ist das Ergebnis einer Aktion
Dem User kann die Möglichkeit gegeben werden aus Aktionen zu wählen.