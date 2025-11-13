# Administration, Systemüberwachung und Prozesse (Ubuntu 24.04)

## 1. Was gehört zur Systemadministration?
Systemadministration umfasst alle Aufgaben, die den Zustand des Systems betreffen.  
Dazu gehören:

- **Dienstverwaltung** (Starten, Stoppen, Neustart, Autostart)  
- **Benutzer- und Rechteverwaltung**  
- **Dateisystempflege** (Mounts, Volumes, Speicherverwaltung)  
- **Log-Analyse**  
- **Netzwerkkonfiguration**  
- **Paketverwaltung** (Installieren, Aktualisieren, Entfernen)  
- **Backup und Wiederherstellung**  
- **Sicherheitskonfiguration** (Firewall, Rechte, Updates)

Kurz: Administration bedeutet, das System funktionsfähig, stabil und sicher zu halten.

---

## 2. Was ist Systemüberwachung?
Systemüberwachung (Monitoring) bedeutet, **Ressourcen, Auslastung und Verhalten** des Systems im Blick zu behalten.  
Dazu gehören:

- **CPU-Auslastung**  
- **RAM-Verbrauch**  
- **Prozesse und deren Verhalten**  
- **Festplattenbelegung und IO**  
- **Netzwerkaktivität und Ports**  
- **System-Logs und Fehlermeldungen**  
- **Dienststatus** (läuft / steht / Fehler)

Ziel: Probleme erkennen, bevor sie kritisch werden.

---

## 3. Prozesse in Linux – Grundbegriffe

**Prozess** – laufendes Programm  
**PID** – eindeutige Prozess-ID  
**PPID** – Elternprozess  
**Daemon** – Hintergrunddienst  
**Zombie** – Prozess beendet, Eintrag noch nicht entfernt  
**Orphan** – Prozess ohne Eltern, wird von systemd übernommen  
**Signal** – Steuerbefehl an Prozesse (z. B. TERM, KILL)

### Prozessbefehle
```bash
ps aux
ps -ef
top
htop
pgrep <name>
pkill <name>
kill <PID>
kill -9 <PID>
```

---

## 4. Systemüberwachung – wichtige Werkzeuge

### Allgemeine Ressourcen
```bash
top        # CPU/RAM/Load
htop       # erweiterte Ansicht
free -h    # Speicher
df -h      # Festplatten
du -sh     # Ordnergröße
uptime     # Laufzeit + Load
vmstat     # Speicher/IO-Statistik
iostat     # IO-Performance
```

### Netzwerk
```bash
ip a
ip r
ss -tulpn
ping <ziel>
traceroute <ziel>
curl <url>
```

---

## 5. Logs und Fehlersuche

Alle Logs unter:
```
/var/log/
```

Wichtige Logdateien:
- **syslog** – allgemeine Meldungen  
- **auth.log** – Login/Authentifizierung  
- **journalctl** – systemd-Logsystem

Beispiele:
```bash
journalctl -u ssh
journalctl -b
journalctl -xe
```

---

## 6. Init-Systeme: init.d und systemd

### init.d – altes System
- basiert auf Shell-Skripten  
- liegt unter `/etc/init.d/`  
- nur noch für Legacy-Dienste

Beispiel:
```bash
sudo /etc/init.d/ssh start
sudo /etc/init.d/ssh stop
```

---

## 7. systemd – aktuelles Init-System in Ubuntu 24.04

### Dienste verwalten
```bash
systemctl start <dienst>
systemctl stop <dienst>
systemctl restart <dienst>
systemctl status <dienst>
```

### Autostart steuern
```bash
systemctl enable <dienst>
systemctl disable <dienst>
```

### Logs eines Dienstes
```bash
journalctl -u <dienst>
```

### Systemsteuerung
```bash
systemctl reboot
systemctl poweroff
systemctl daemon-reload
```

---

## 8. Wichtige systemd-Begriffe (für Verständnis)

**Unit** – grundlegende Konfigurationseinheit (service, timer, socket …)  
**Service Unit** – beschreibt einen Dienst  
**Timer Unit** – zeitgesteuerte Jobs  
**Target** – Gruppe von Units (ähnlich Runlevel)  
**Socket Unit** – startet Dienste bei Bedarf  

---

## 9. Vergleich: init.d vs systemd

| Thema | init.d | systemd |
|-------|--------|---------|
| Status | alt | Standard |
| Skripte | Shell | Unit-Dateien |
| Logs | /var/log | journalctl |
| Parallelisierung | schwach | stark |
| Funktionsumfang | begrenzt | sehr umfangreich |

---

## Kurzes Fazit
Systemadministration = Dienste, Logs, Benutzer, Netzwerk, Pakete.  
Monitoring = beobachten, messen, prüfen.  
systemd = das zentrale Werkzeug für Dienste unter Ubuntu 24.04.
