---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
Alle Elemente in der Benutzeroberfläche haben die Superklasse `android.view.View`
Standardobjekte:
- TextView
- Button
- CheckBox
- Progressbar

# View Groups
---
Ein View kann aus mehren Views zusammengesetzt werden (z.B. `RadioGroup` ist aus mehreren `RadioButtons` zusammengesetzt) 

`ViewGroups` bestehen aus einem einzigen übergeordneten View, das von der Klasse: `android.view.ViewGroup` erbt und deshalb auch als Container-View bezeichnet wird. Dieser enthält die untergeordneten Views.