# Bash und Paketverwaltung (Ubuntu 24.04)

## 1. Bash – Grundidee
Die Bash ist die zentrale Arbeitsumgebung unter Ubuntu.  
Sie dient nicht nur zum Eingeben von Befehlen – sie ist eine **Automatisierungs- und Kontrollschicht**, über die praktisch alles im System gesteuert wird.

Warum wichtig:
- Headless-Server haben kein GUI → alles läuft über Bash  
- DevOps- und Cloud-Tools arbeiten fast immer skriptbasiert  
- Konfiguration, Logs, Dienste, Netzwerk – alles gesteuert über Befehle  
- Wiederholbarkeit: alles, was in der Bash steht, kann in Skripte automatisiert werden  

Die Bash ist somit **Kernkompetenz Nr. 1** im Linux-Umfeld.

---

## 2. Grundbefehle – nicht nur “wie”, sondern “warum”

### Navigation
Wird benutzt, um im Dateisystem effizient zu arbeiten:
```bash
ls
cd <pfad>
pwd
```

### Dateien/Ordner verwalten
Ohne GUI braucht man direkte Befehle für Kopieren, Verschieben, Löschen:
```bash
cp quelle ziel
mv quelle ziel
rm datei
mkdir neuer_ordner
```

Warum wichtig:
- Konfigurationsdateien befinden sich überall im System  
- Backups, Sicherung, Logsortierung – alles über Dateibefehle  

### Inhalte anzeigen
Wird für Loganalyse, Fehlersuche und Konfiguration benötigt:
```bash
cat datei
less datei
tail -f logfile
```

### Suchen
Unersetzlich, wenn du Fehler, Konfigurationen oder Dateien finden musst:
```bash
grep "wort" datei
find /pfad -name "dateiname"
```

### Verlauf / Hilfe
Zum Lernen und Nachschlagen:
```bash
history
man <befehl>
```

### Pipes
Erlauben das Kombinieren von Tools:
```bash
ps aux | grep ssh
```
Pipes machen aus mehreren kleinen Programmen mächtige Werkzeuge.

### Umleitungen
Steuern, wo Daten herkommen und wohin sie gehen:
```bash
echo "text" > datei
echo "text" >> datei
sort < input.txt
```

Warum wichtig:
- Logs filtern  
- Outputs speichern  
- Reports erstellen  
- Daten transformieren  

---

## 3. Variablen und Umgebungsvariablen – wie Linux intern denkt
In der Bash werden Werte nicht “irgendwo” gespeichert – sie sind **Teil der Laufzeitumgebung**.

### Lokale Variablen
```bash
name="test"
echo $name
```

### Umgebungsvariablen
```bash
export PATH=$PATH:/opt/tools
```

Wichtige Variablen:
- `$HOME` → persönlicher Bereich  
- `$USER` → aktueller Benutzer  
- `$PATH` → Wo die Shell Programme sucht  
- `$PWD` → aktuelles Verzeichnis  

Warum das wichtig ist:
- Tools funktionieren nur, wenn `$PATH` stimmt  
- Dienste können falsche Umgebungen haben  
- Konfigurationsfehler entstehen oft durch “falsche” Variablen  

---

## 4. Bash-Skripte – die Grundlage der Automatisierung
Skripte ermöglichen reproduzierbare Abläufe statt “manuell rumklicken”.

### Einfaches Skript
```bash
#!/bin/bash
echo "Hallo Welt"
```

### Ausführbar machen
```bash
chmod +x script.sh
```

Warum wichtig:
- Server-Konfiguration automatisieren  
- Installationen standardisieren  
- CI/CD-Jobs definieren  
- Systemchecks planen  

DevOps = Skripten, Versionieren, Ausführen.

---

## 5. Paketverwaltung (APT) – das Software-Management von Ubuntu
APT ist das Werkzeug, mit dem Ubuntu **Software installiert, aktualisiert und verwaltet**.

### Update & Upgrade
```bash
sudo apt update
sudo apt upgrade
```
Warum:
- `update` aktualisiert Paketlisten  
- `upgrade` installiert neue Versionen  
- Sicherheitspatches kommen über APT  

### Installation & Entfernung
```bash
sudo apt install <paket>
sudo apt remove <paket>
sudo apt purge <paket>
sudo apt autoremove
```
Warum:
- `remove` lässt Konfigs stehen  
- `purge` entfernt auch Konfigs  
- `autoremove` räumt Abhängigkeiten weg  

### Suche / Infos
```bash
apt search <paket>
apt show <paket>
dpkg -l
```

Warum wichtig:
- Versionen prüfen  
- Abhängigkeiten verstehen  
- Fehlerdiagnose wenn Pakete fehlen  

---

## 6. snap – alternative Paketquelle
Snap bringt Container-artige Pakete. Wird seltener genutzt, aber ist noch Teil von Ubuntu 24.04.

### Snap-Befehle
```bash
snap install <paket>
snap remove <paket>
snap list
```

Snap ist wichtig zu verstehen, weil manche Programme **nur** als Snap verfügbar sind.

---

## 7. Warum Bash + Paketmanager untrennbar sind
Beide Bausteine gehören zusammen:

### Bash ermöglicht:
- Steuerung  
- Automatisierung  
- Fehleranalyse  
- Skripte  
- Systemlogik

### APT ermöglicht:
- Installation  
- Wartung  
- Updates  
- Sicherheit  

Zusammen bilden sie die Grundlage jeder Systemintegration – egal ob physischer Server, Cloud-VM, Container oder CI/CD-Runner.

Ohne Bash → keine Automatisierung.  
Ohne APT → keine kontrollierte Softwareverwaltung.

Beides zusammen = Basiskompetenz im DevOps-Stack.
