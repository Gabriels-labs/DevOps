# Virtualisierung und Cloud Computing

## 1. Was ist Virtualisierung?
Virtualisierung bedeutet, dass **physische Ressourcen in mehrere unabhängige, isolierte Umgebungen aufgeteilt** werden.  
Eine Hardware kann mehrere virtuelle Systeme bereitstellen.  
Ziel: flexible Ressourcennutzung, geringere Kosten und einfache Verwaltung.

---

## 2. Typen der Virtualisierung (Use-Case)

### 2.1 Desktop Virtualization (VDI)
Virtuelle Desktops laufen auf einem Server, Benutzer greifen remote darauf zu.  
**Vorteile:** zentrale Verwaltung, hohe Sicherheit, Zugriff von jedem Gerät.

### 2.2 Application Virtualization
Anwendungen laufen in isolierten Umgebungen, ohne Installation auf dem lokalen System.  
**Vorteile:** keine Versionskonflikte, schnelle Bereitstellung, zentrale Updates.

### 2.3 Server Virtualization
Mehrere virtuelle Server nutzen eine gemeinsame physische Hardware.  
**Vorteile:** bessere Auslastung, geringere Kosten, einfache Wartung.

---

## 3. Technische Arten der Virtualisierung

### 3.1 Platform Virtualization
Virtualisierung kompletter Plattformen:
- OS-Virtualisierung  
- Application Virtualization  
- Emulation  

### 3.2 Resource Virtualization
Virtualisierung einzelner Ressourcen:
- CPU-Virtualisierung  
- Speicher-Virtualisierung (RAM)  
- Storage-Virtualisierung  
- Netzwerk-Virtualisierung  

---

## 4. Arten der Server-Virtualisierung

### 4.1 Full Virtualization
Die Gast-OS erkennt nicht, dass sie virtuell ist.  
**+** hohe Kompatibilität  
**–** höhere Last durch Emulation

### 4.2 Paravirtualization
Die Gast-OS kommuniziert direkt mit dem Hypervisor.  
**+** sehr gute Performance  
**–** benötigt angepasste Systeme

### 4.3 OS-Level Virtualization (Container)
Ein Kernel, viele isolierte Container.  
**+** sehr effizient, schnell  
**–** keine unterschiedlichen Betriebssysteme möglich

---

## 5. Hypervisor

Ein Hypervisor erstellt und verwaltet virtuelle Maschinen.

### Typ 1 – Bare-Metal Hypervisor
Läuft direkt auf der Hardware.  
**Beispiele:** VMware ESXi, Hyper-V Server, KVM, Xen  
**Vorteile:** hohe Performance, stabil für Rechenzentren

### Typ 2 – Hosted Hypervisor
Läuft auf einem bestehenden Betriebssystem.  
**Beispiele:** VirtualBox, VMware Workstation, Parallels  
**Vorteile:** ideal für Tests und Lernumgebungen

---

## 6. Bekannte Virtualisierungsplattformen
- **VMware ESXi** – Standard für professionelle Virtualisierung  
- **KVM** – Hypervisor im Linux-Kernel, Open Source  
- **Microsoft Hyper-V** – in Windows Server integriert  
- **Citrix** – stark im Bereich VDI  
- **OpenVZ / LXC** – Container-Virtualisierung  
- **vStack** – Plattform für hybride Infrastrukturen  

---

# Cloud Computing

## 7. Was ist Cloud Computing?
Cloud Computing stellt IT-Ressourcen wie Rechenleistung, Speicher, Datenbanken und Software **über das Internet** bereit.  
Bezahlung erfolgt nach Nutzung (*Pay-as-you-go*).  
Ziel: flexibel, skalierbar und ohne eigene Hardware arbeiten.

---

## 8. Vorteile für Unternehmen
- Skalierbarkeit  
- Kostenersparnis  
- Hohe Verfügbarkeit  
- Schnelle Bereitstellung  
- Globale Erreichbarkeit  
- Automatische Updates und Patches  
- Moderne Sicherheitsfunktionen  

---

## 9. Cloud-Bereitstellungsmodelle

### 9.1 Public Cloud
Bereitgestellt durch Provider wie Azure, AWS oder Google Cloud.  
**Vorteile:** günstig, flexibel, keine eigene Hardware nötig.

### 9.2 Private Cloud
Nur für ein Unternehmen – lokal oder extern betrieben.  
**Vorteile:** volle Kontrolle, hohe Sicherheit.

### 9.3 Hybrid Cloud
Kombination aus Public und Private Cloud.  
**Vorteile:** flexibel, ideal für große Unternehmen.

### 9.4 Multi-Cloud
Nutzung mehrerer Public Clouds gleichzeitig.  
**Vorteile:** weniger Abhängigkeit, höhere Verfügbarkeit.

---

## 10. Cloud-Service-Modelle

### IaaS – Infrastructure as a Service
Virtuelle Maschinen, Netzwerke, Storage.  
**Beispiele:** AWS EC2, Azure VM.

### PaaS – Platform as a Service
Komplette Plattform für die Entwicklung und Ausführung von Anwendungen.  
**Beispiele:** Azure App Service, Google App Engine.

### SaaS – Software as a Service
Fertige Anwendungen, die direkt genutzt werden können.  
**Beispiele:** Microsoft 365, Gmail.

