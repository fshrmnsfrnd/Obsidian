---
Fach:
Thema:
  - "[[KI]]"
---
Fine Tuning von LLMs passiert nach dem initialen Training. Hier können der LLM neue Dinge beigebracht werden

# Daten für Fine Tuning
- Instruktion
- Input
- Output
# Parameter-effizientes Fine Tuning
Es gibt 2 verschiedene Arten dafür:
## Adapter
Man fügt vor und nach dem Feedforward Layer in jedem [[Transformer#Transformer Block|Transformer Block]] einen Adapter ein, und passt dessen Gewichte an.

## Low-Rank Adaption (LoRA)
Hier wird nur eine bestimmte Anzahl von Parametern neu gewichtet.