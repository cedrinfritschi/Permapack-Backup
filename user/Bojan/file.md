# IT-Infrastruktur & Backup-Zusammenfassung

## 👥 Unternehmen & Teams
- **Mitarbeitende:** 320
- **Abteilungen:** Informatik, HR, Logistik, Einkauf/Verkauf, ERP (Einkauf/Verkauf)
- **ERP:** In die Cloud verschoben, Server noch vorhanden, aber Daten nicht mehr relevant

### IT-Team:
- 2 Infrastrukturverantwortliche
- 4 ERP-Mitarbeiter
- 1 Supporter
- 1 Lernender

## 🖥️ Infrastruktur
- **Clients:** 390 (Workstations & All-in-One-Geräte)
- **Server:** 88 total (82 virtuell, 5 physikalisch)
- **Produktive Server:** 57 Server mit 65 TB zu sichernder Daten
- **ESXi-Hosts:** identisch aufgebaut, 3 Rechenzentren, VMs laufen auf NAS

### NAS-Systeme:
- **RZ1:** Synology RS3621xs+, 16×4TB SSD, RAID 6
- **RZ2:** Synology RS4017xs+, 28×8TB HDD, RAID 5
- **Speicher gesamt:** 115 TB verfügbar auf NAS (ohne Tape)
- **Citrix-Klon:** reduziert Speicherbedarf
- **USV:** Alle RZs, halten 20 Minuten

## 🔒 Backup & Datensicherung
### Tools & Systeme
- **Veeam Backup & Replication On-Prem**
- **Veeam 365 für Office 365 Cloud-Backups** (seit April 2022)
- **Cloud-Backup-Lösung** (SharePoint, Teams, Exchange)
  - 11 TB produktiv, +15 GB/Tag Zunahme
  - 1.3 TB zusätzliche Sicherung

### Lizenzierung
- 265 Office-Lizenzen
- 260 Benutzer
- 320 Postfächer
- 55 Teams
- 10 SharePoint-Seiten
- 8-Socket-Lizenz (CHF 10'000)
- VM-Lizenzierung wird neu geplant

### Backup-Jobs
- **VM1 & VM2:** Veeam B&R + Veeam 365 auf NAS
- **Userdaten:** 19:00–20:00
- **SharePoint:** 20:00–20:30
- **Low Priority:** 20:00 (15–45 Min)
- **High Priority:** 23:00–23:30
- **Copy Jobs:** laufen kontinuierlich

### Backup-Strategie
- Synthetic Full Backup
- Komprimierung
- Application-Aware Processing (z. B. DC/SQL)
- Copy Jobs bis 1 Jahr
- **Backup Worker (3x):** deduplizieren Datenübertragung

## 📼 Tape Backup
- **Hardware:** HPE 1/8 G2 Tape Autoloader (8 Tapes + 1 Cleaning Tape, Mail Slot vorhanden)
- **Bänder:**
  - 8 Tagesbänder
  - 68 Wochenbänder (5 Bänder/Woche)
  - 1 Jahresband
  - Zufallstest im November
- **Rotation:**
  - Tägliches Wechseln
  - Tape → Gebäude 1 → Tresor (lichtgeschützt, kühl, trocken)
- **Datenträgerkontrolle:** RAID vorhanden
- **Backup-Routing:** NAS SSD → Tape (5 Jobs)
- **Restore-Zeiten dokumentiert**
- **Kein Direkt-Restore von Exchange in die Cloud**

## 🛡️ Notfallkonzept & Sicherheit
### Dokumentation & Prozesse
- Notfallkonzept (seit 2020) inkl. Wiederherstellungsplan, Kommunikationskonzept
- Krisen-WhatsApp-Gruppe, Telefonliste (Papier), Kommunikationskonzept (Schublade)

### Wiederherstellungszeiten
- **vCenter:** 2h
- **DC:** 2h
- **Benutzerprofile:** 4h
- **ERP:** 12h
- **Filesystem:** 4h
- **Esko:** 24h
- **ESXi Hosts:** 12h
- **Analysephase:** bis 48h
- **Gesamter Restore-Prozess:** bis 11 Tage

### Tests
- Notfallübungen
- Restore eines Files, einer Mail und eines Servers
- USV-Stromausfalltest
- Jahresband & Zufallstests

## 🛡️ Cyber Defense
- **Überwachung:** PRTG, Pikett vorhanden
- **Externe Partner:** Security Incident Response Teams
- **Red Team:** 1× jährlich (externes Audit & Penetrationstest)
- **Awareness:** Kampagnen, Schulungsplattform, Phishing-Tests

## 📜 Service-Level-Agreements (SLA)
- **Supportzeiten:** 08:00–17:00
- **Proaktive Überwachung:** 06:00–22:00
- **Reaktionszeit:** innerhalb 1 Stunde
