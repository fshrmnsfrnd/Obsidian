---
Thema:
  - "[[Windows Client]]"
---
- **A**ccounts 
- **G**lobal Groups 
- **D**omain **L**ocal Groups 
- **P**ermissions

>Die AGDLP-Regel ist ein Best-Practice-Konzept für die Rechtevergabe in Microsoft Active Directory-Umgebungen. Sie wird für die Role-Based Access Control ([[RBAC]]) verwendet
# Vorteile
---
- **Zentrale Verwaltung**: Berechtigungen werden nur an einer Stelle vergeben.
- **Skalierbarkeit**: Einfache Erweiterung bei wachsenden Organisationen.
- **Übersichtlichkeit**: Klare Struktur der Rechtevergabe.
- **Wartbarkeit**: Änderungen sind schnell und sicher durchführbar.
- **Fehlerminimierung**: Reduziert das Risiko von Fehlkonfigurationen.
# AGDLP Prinzip
---
1. (**A**) Benutzer erstellen
2. (**G**) Benutzer nach Funktion/Abteilung in Global Groups aufnehmen
3. (**DL**) Global Groups den Domain Local Groups nach Ressourcen zuweisen
4. (**P**) Berechtigungen an Domain Local Groups vergeben