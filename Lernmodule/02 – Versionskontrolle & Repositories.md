# 02 – Versionskontrolle & Repositories

## 1. Git – Grundprinzip
Git ist ein **verteiltes Versionskontrollsystem**. Jede Arbeitskopie enthält ein vollständiges Repository.  
Ziel: Änderungen nachvollziehbar machen, parallel arbeiten können, saubere Historie behalten.

Wichtige Begriffe:
- **Repository**: Projekt + komplette Historie  
- **Commit**: gespeicherte Änderung  
- **Branch**: parallele Entwicklungs­linie  
- **Merge**: Änderungen zusammenführen  
- **Remote**: z. B. GitHub- oder GitLab-Server

---

## 2. Git Flow – Strukturierter Workflow
Git Flow definiert, wie Entwicklungszweige organisiert sind.

Standardaufbau:
- **main** → stabile Versionen  
- **develop** → aktive Entwicklung  
- **feature/** → neue Funktionen  
- **release/** → Vorbereitung auf Release  
- **hotfix/** → schnelle Fehlerkorrekturen in main

Ziel: Ordnung, klare Abläufe, nachvollziehbare Releases.

---

## 3. Grundbefehle in Git (Arbeitsalltag)
- `git init` – neues Repo  
- `git clone` – Projekt herunterladen  
- `git status` – Überblick über Änderungen  
- `git add` – Dateien für Commit vormerken  
- `git commit -m ""` – Änderungen speichern  
- `git log` – Historie  
- `git branch` / `git switch` – Zweige verwalten  
- `git merge` – Branch zusammenführen  
- `git pull` – Änderungen holen + mergen  
- `git push` – eigene Änderungen hochladen  

---

## 4. GitHub & GitLab – Überblick
Beides sind **Remote-Hosting-Plattformen** für Git-Repositories.

### GitHub
- Fokus auf Open Source und Community  
- GitHub Actions für CI/CD  
- Sehr verbreitet in DevOps, Cloud und Ausbildung  

### GitLab
- Stärker auf Unternehmen ausgerichtet  
- Integrierte CI/CD-Pipelines direkt im Core  
- Selbst gehostete Varianten möglich

Zweck beider Plattformen:
- Repositories zentral speichern  
- Zusammenarbeit organisieren  
- Issues, Pull Requests, Reviews  
- Automatisierung (CI/CD)

---

## 5. Ziel dieses Lernfelds
Sicher mit Git umgehen, Branching-Strategien verstehen, Repositories erstellen, Workflows sauber anwenden und Remote-Dienste im Alltag nutzen können.
