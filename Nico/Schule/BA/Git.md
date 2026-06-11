---
Fach: "[[BA]]"
---
# Anfangs-Config
```bash
git config --global user.name "Dein Name"
git config --global user.email "mail@example.com"
git config --global init.defaultBranch main
```
# Git Commands
---

| Befehl                                          | Beschreibung                                                |
| ----------------------------------------------- | ----------------------------------------------------------- |
| `git init`                                      | Neues Repository initialisieren                             |
| `git clone <url>`                               | Repository klonen                                           |
| `git status`                                    | Zustand des Repos anzeigen                                  |
| `git add <datei>` / `git add .`                 | Änderungen stagen                                           |
| `git commit -m "msg"`                           | Commit erstellen                                            |
| `git log`                                       | Commit-Verlauf · `--oneline` · `--graph`                    |
| `git diff`                                      | Nicht gestagete Änderungen anzeigen                         |
| `git branch`                                    | Branches auflisten                                          |
| `git branch <name>`                             | Neuen Branch erstellen                                      |
| `git checkout <branch>` / `git switch <branch>` | Branch wechseln                                             |
| `git merge <branch>`                            | Branch in aktuellen mergen                                  |
| `git remote add <origin> <url>`                 | Remote hinzufügen                                           |
| `git push [<origin> <branch>]`                  | Änderungen hochladen                                        |
| `git pull`                                      | Änderungen herunterladen & mergen / rebase                  |
| `git fetch`                                     | Holt die Änderungen von remote, Merged / Rebased aber nicht |
| `git stash`                                     | Änderungen beiseitelegen · `git stash pop` zurückholen      |
