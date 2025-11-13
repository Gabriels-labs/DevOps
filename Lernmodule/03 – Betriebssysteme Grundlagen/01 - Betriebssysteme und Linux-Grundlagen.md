# Betriebssysteme und Linux-Grundlagen

## 1. Was ist ein Betriebssystem?
Ein Betriebssystem (OS) ist die zentrale Software, die Hardware verwaltet und Anwendungen ausführt.  
Aufgaben des OS:
- Ressourcenverwaltung (CPU, RAM, Speicher, Geräte)
- Prozess- und Speicherverwaltung
- Dateisystem und Benutzerrechte
- Schnittstelle zwischen Benutzer und Hardware

Beispiele: Windows, Linux, macOS.

---

## 2. Architektur eines Betriebssystems
Typische Komponenten:
- **Kernel**  
  Kern des Systems, verwaltet Hardware, Prozesse und Speicher.
- **Treiber**  
  Verbindung zwischen Kernel und Hardware.
- **Systembibliotheken**  
  Gemeinsame Funktionen für Anwendungen.
- **User Space**  
  Programme, Shell, grafische Oberflächen.
- **Dateisysteme**  
  z. B. ext4, NTFS, FAT32.

Linux-Architektur: klar getrennt in Kernel + User Space, modular aufgebaut, viele austauschbare Komponenten.

---

## 3. Linux-Distributionen
Ein Linux-System besteht aus:
- Linux-Kernel  
- Systemwerkzeugen  
- Paketmanager  
- Desktop- oder Server-Umgebung

Distribution = Paket aus Kernel + Software-Auswahl + Paketverwaltung.

Beispiele:
- **Ubuntu / Debian** – leicht zu bedienen, große Community  
- **CentOS / RHEL / AlmaLinux** – serverorientiert  
- **Arch Linux** – minimalistisch, rolling release  
- **openSUSE** – stabil, gut für Administration  

Wichtig: Der Kernel ist überall ähnlich, Unterschiede liegen in Tools, Paketen, Struktur.

---

## 4. Bootvorgang (Startprozess)
Allgemeiner Ablauf:
1. **Firmware** (BIOS/UEFI) startet Hardware-Initialisierung  
2. **Bootloader** (z. B. GRUB) wird geladen  
3. Bootloader lädt Kernel + initramfs  
4. Kernel initialisiert Geräte, startet PID 1  
5. **Init-System** (z. B. systemd) startet Dienste  
6. Login-Shell oder Desktop-Umgebung wird angezeigt

Uefi → moderne Systeme, unterstützt Secure Boot, schnellere Initialisierung.

---

## 5. Installation eines Betriebssystems
Grundschritte:
- Boot-Medium erstellen (USB)  
- Boot-Reihenfolge einstellen  
- Partitionierung auswählen (automatisch oder manuell)  
- Benutzer und Passwort anlegen  
- Basissoftware installieren  
- Nach der Installation: Treiber, Updates, Netzwerk prüfen

Bei Linux-Distributionen ist der Installationsprozess meist standardisiert und in wenigen Schritten abgeschlossen.

