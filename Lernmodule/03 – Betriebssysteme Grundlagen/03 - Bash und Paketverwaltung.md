# Bash und Paketverwaltung (Ubuntu 24.04)

## Bash – Grundidee
Bash ist die wichtigste Shell unter Linux.  
Sie ermöglicht das Ausführen von Befehlen, das Arbeiten mit Variablen, Pipes und einfachen Skripten.  
Die Bash bildet die Basis für Administration, Automatisierung und tägliche Systemarbeit in Ubuntu.

Warum wichtig:
- Headless-Server haben kein GUI → alles läuft über Bash  
- DevOps- und Cloud-Tools arbeiten fast immer skriptbasiert  
- Konfiguration, Logs, Dienste, Netzwerk – alles gesteuert über Befehle  
- Wiederholbarkeit: alles, was in der Bash steht, kann in Skripte automatisiert werden  

---

## Eingebaute Bash-Befehle

**break** – beendet eine for/while/until-Schleife  
**continue** – startet die nächste Schleifeniteration  
**echo** – gibt Text oder Variablen aus  
**exit** – beendet die aktuelle Shell oder ein Skript  
**export** – macht Variablen für Unterprozesse verfügbar  
**hash** – speichert vollständige Pfade von Befehlen  
**kill** – sendet Signale an Prozesse  
**pwd** – zeigt das aktuelle Arbeitsverzeichnis  
**read** – liest Eingaben in Variablen  
**return** – beendet eine Funktion mit Rückgabewert  
**shift** – verschiebt Positionsparameter nach links  
**test** – führt logische Vergleiche aus  
**times** – zeigt Benutzer- und Systemzeit der Shell  
**trap** – führt Befehle bei bestimmten Signalen aus  
**unset** – entfernt Variablen  
**wait** – wartet auf Kindprozesse

---

## Bash-Skripte

### Shebang
```bash
#!/bin/bash
```

### Kommentare
`#` – Kommentarzeile

### Grundlagen
```bash
variable="text"
echo $variable
```

---

## Wichtige reservierte Variablen

**$DIRSTACK** – Verzeichnisstack  
**$EDITOR** – Standardeditor  
**$EUID** – effektive UID  
**$UID** – reale UID  
**$FUNCNAME** – Name der aktuellen Funktion  
**$GROUPS** – Gruppen des aktuellen Benutzers  
**$HOME** – Home-Verzeichnis  
**$HOSTNAME** – Hostname  
**$HOSTTYPE** – Architektur  
**$LC_CTYPE** – Zeichencodierung  
**$OLDPWD** – vorheriges Verzeichnis  
**$OSTYPE** – Betriebssystemtyp  
**$PATH** – Suchpfad für Befehle  
**$PPID** – Elternprozess-ID  
**$SECONDS** – Laufzeit eines Skripts  
**$#** – Anzahl der übergebenen Parameter  
**$*** – alle Parameter in einer Zeile  
**$@** – alle Parameter zeilenweise  
**$!** – PID des letzten Hintergrundprozesses  
**$$** – PID des aktuellen Skripts

---

## Bedingungen (if-then-else)

### Grundstruktur
```bash
if <befehl oder ausdruck>
then
    <aktion bei wahr>
else
    <aktion bei falsch>
fi
```

### Beispiel
```bash
#!/bin/bash

source=$1
dest=$2

if [[ "$source" -eq "$dest" ]]
then
    echo "Quelle und Ziel sind identisch!"
    exit 1
else
    cp "$source" "$dest"
    echo "Kopieren erfolgreich!"
fi
```

---

## Logische Operatoren

**-z** – String ist leer  
**-n** – String ist nicht leer  
**=**, **==** – Strings gleich  
**!=** – Strings ungleich  
**-ne** – nicht gleich  
**-lt** – kleiner  
**-le** – kleiner oder gleich  
**-gt** – größer  
**-ge** – größer oder gleich  
**!** – Negation  
**-a**, **&&** – logisches UND  
**-o**, **||** – logisches ODER  

---

## Paketverwaltung (APT)

### Grundbefehle

#### Aktualisierung
```bash
sudo apt update
sudo apt upgrade
```

#### Installation / Entfernung
```bash
sudo apt install <paket>
sudo apt remove <paket>
sudo apt purge <paket>
sudo apt autoremove
```

#### Suche / Infos
```bash
apt search <paket>
apt show <paket>
dpkg -l
```

---

## Repositories hinzufügen

### Beispielsyntax
```bash
sudo add-apt-repository 'deb http://repository_address version branch'
```

### GPG-Schlüssel hinzufügen (falls nötig)
```bash
sudo apt-key adv --fetch-keys 'URL'
```

---

## Warum dieser Abschnitt wichtig ist
Bash + APT bilden die Grundlage für Dateioperationen, Systemskripte, Automatisierung und Softwareverwaltung in Ubuntu-Umgebungen.
