# Systemkonfiguration, Dateisystem und Benutzerrechte (Ubuntu 24.04)

## 1. Grundlegende System- und Netzwerkkonfiguration
Ubuntu 24.04 nutzt moderne Standards: `systemd` für Dienste, `netplan` für Netzwerke und `apt` für Paketverwaltung.  
Die meisten Einstellungen laufen über Terminal oder Konfigurationsdateien.

---

## 2. Dateisystem unter Linux – Grundprinzip
Linux arbeitet nach dem **„Alles ist eine Datei“**–Prinzip.  
Das bedeutet:

- Geräte → erscheinen als Dateien unter `/dev`  
- Prozesse → erscheinen unter `/proc`  
- Konfiguration → Textdateien unter `/etc`  
- Benutzerordner → `/home/<user>`  
- Systemprogramme → unter `/bin`, `/usr/bin`, `/sbin`

Die Struktur ist **hierarchisch**, beginnend bei `/` (Root).  
Es gibt **keine Laufwerksbuchstaben** wie C: oder D:.  
Stattdessen werden Partitionen und Geräte in die Baumstruktur „eingehängt“ (mounten).

Wichtige Punkte:
- Der Kernel sitzt im `/boot`–Bereich  
- Temporäre Daten liegen oft in `/tmp` oder `/var`  
- Große Softwarepakete und Bibliotheken liegen in `/usr`  

Das Konzept sorgt dafür, dass Linux **auf jedem Gerät gleich funktioniert** – egal ob Server, Desktop oder Container.

---

## 3. Benutzer und Gruppen – wie das Modell funktioniert
Ubuntu/Linux benutzt ein **Mehrbenutzer-Konzept**.  
Jeder Benutzer hat:

- eine eindeutige **UID**  
- eine oder mehrere **Gruppen** (GID)  
- ein eigenes Home-Verzeichnis  
- eigene Rechte auf Dateien und Prozesse  

### Warum gibt es Gruppen?
Gruppen erleichtern die Rechtevergabe.  
Man gibt nicht jedem Benutzer einzeln Rechte, sondern einer Gruppe, und Benutzer erben diese Rechte automatisch.

Beispiele:
- Gruppe `sudo` → Benutzer darf administrative Befehle ausführen  
- Gruppe `adm` → Zugriff auf Systemlogs  
- Eigene Projektgruppen → für geteilte Ordner  

### Wie Linux entscheidet, wer was darf
Jede Datei hat drei Ebenen:

1. **owner** (Besitzer)  
2. **group** (zugeordnete Gruppe)  
3. **others** (alle anderen)

Jede Ebene hat ihre Rechte:
- **r** (lesen) - (4)
- **w** (schreiben) - (2)  
- **x** (ausführen) - (1) 

Beispiel:
-rw-r----- 1 user team 2048 datei.txt - mit Befehle "chmod 640 datei.txt"

Heißt:
- Besitzer darf lesen + schreiben  
- Gruppe darf nur lesen  
- Andere dürfen nichts  

### Warum ist das wichtig in DevOps und Systemintegration?
- Konfigurationsdateien müssen über Gruppen sauber abgesichert werden  
- Dienste laufen nicht als root, sondern unter eigenen Service-Accounts  
- Rechte beeinflussen direkt das Verhalten von Webservern, Skripten und CI/CD-Pipelines  
- Sicherheit und Stabilität hängen stark von korrekten Datei- und Prozessrechten ab  

Die Befehle (`adduser`, `usermod`, `chmod`, `chown`) sind nur Werkzeuge – entscheidend ist das Modell dahinter und wie Linux Zugriffe steuert.
