# Bash und Paketverwaltung (Ubuntu 24.04)

## 1. Bash – Grundidee
Die Bash ist der Standard-Kommandointerpreter unter Ubuntu.  
Sie steuert Befehle, Skripte, Variablen und Automatisierungen. Für Server- und DevOps-Arbeit ist sie das Hauptwerkzeug.

---

## 2. Grundbefehle der Bash

### Navigation
```bash
ls
cd <pfad>
pwd
```

### Dateien/Ordner
```bash
cp quelle ziel
mv quelle ziel
rm datei
mkdir neuer_ordner
```

### Inhalte anzeigen
```bash
cat datei
less datei
tail -f logfile
```

### Suchen
```bash
grep "wort" datei
find /pfad -name "dateiname"
```

### Verlauf / Hilfe
```bash
history
man <befehl>
```

### Pipes
```bash
ps aux | grep ssh
```

### Umleitungen
```bash
echo "text" > datei
echo "text" >> datei
sort < input.txt
```

---

## 3. Variablen und Umgebungsvariablen

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
- $HOME  
- $USER  
- $PATH  
- $PWD  

---

## 4. Bash-Skripte

### Einfaches Skript
```bash
#!/bin/bash
echo "Hallo Welt"
```

### Ausführbar machen
```bash
chmod +x script.sh
```

Skripte werden genutzt für:
- Automatisierung  
- Installationen  
- Checks  
- wiederkehrende Aufgaben  

---

## 5. Paketverwaltung unter Ubuntu 24.04 (APT)
APT ist das Standardwerkzeug für Installation, Updates und Entfernung von Software.

### Update & Upgrade
```bash
sudo apt update
sudo apt upgrade
```

### Installation & Entfernung
```bash
sudo apt install <paket>
sudo apt remove <paket>
sudo apt purge <paket>
sudo apt autoremove
```

### Suche / Infos
```bash
apt search <paket>
apt show <paket>
dpkg -l
```

---

## 6. snap (optional)
Snap wird in Ubuntu 24.04 weiterhin unterstützt, aber weniger genutzt.

### Snap-Befehle
```bash
snap install <paket>
snap remove <paket>
snap list
```

---

## 7. Warum Bash + Paketmanager wichtig sind
Bash + APT sind Grundlage für:
- Automatisierte Provisionierung  
- Installationsskripte  
- Serverkonfiguration  
- CI/CD-Umgebungen  
- Reproduzierbare Deployments  

Ohne Bash und Paketverwaltung gibt es praktisch keine Systemintegration oder DevOps-Arbeit auf Ubuntu.
