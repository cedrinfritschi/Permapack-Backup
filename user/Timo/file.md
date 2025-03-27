# **Permapack IT & Datensicherung**

## **IT Rollen**
- **Infrastruktur**
- **Enterprise Infrastructure Planning**
- **Supporter**
- **Lernende**

---

## **Datensicherung**
### **Übersicht Infrastruktur**
- **400 Clients** (größtenteils Clients)
- **88 Server** (82 virtuell / 5 physikalisch)
- **3 Rechenzentren**
- **Backup-Lösung:** Veeam Backup & Replication
- **M365 Backup:**  
  - 265 Lizenzen (Kosten: 5.500 CHF)
  - 260 User
  - 320 Postfächer
  - 55 Teams-Gruppen
  - 10 SharePoint-Seiten
- **Backup-Daten:**
  - **Gesamt:** 11 TB Backup
  - **Produktivdaten:** 1,3 TB Source-Daten (+15 GB pro Tag)
  - **Speicherung:** Backup auf produktivem Storage einer VM

---

## **Veeam Backup & Replication**
- **Lizenzen:** 8 Sockets (Kosten: 10.000 CHF pro Jahr)
- **Backup-Performance:**
  - 3 Worker zur Backup-Beschleunigung
  - Jeder ESX-Host hat einen eigenen Worker
- **Gesicherte Daten:**
  - **57 Server**
  - **65 TB Source-Daten**
  - **115 TB Backups** (direkt auf NAS verfügbar)
- **Backup-Strategie:**
  - High-Server: 14 Snapshots
  - Low-Server: 7 Snapshots
  - **Backup läuft durchgehend**
  - **Synthetic Full Backup** (wöchentlich)
  - **Application-Aware Processing**
  - Kopien werden bis zu **1 Jahr** in einem Copy-Job gespeichert

### **Backup-Speicher**
- **1x NAS:** 16x 4 TB SSD
- **1x NAS:** 28x 8 TB HDD
- **LTO 9 Tape:** 11 TB (komprimierte Daten, nicht 30 TB)
- **HPE Tape Autoloader**
  - **1 Cleaning Tape**
  - **8 Tagesbänder** (Aufbewahrung: 1-2 Wochen)
  - **68 Wochenbänder** (Aufbewahrung: 2-3 Monate)
  - **Monatsbänder** (Aufbewahrung: 3-6 Monate)
  - **Jahresbänder** (Test zu Beginn, Aufbewahrung: 10 Jahre)
- **Lagerung:**
  - Tapes werden im Tresor aufbewahrt
  - **Zufallstests im November** (Funktion des Bandes, Cloud Restore, Wiederherstellungszeit, Test-VM-Größe)

---

## **Backup Jobs**
- **Tägliche Sicherung**
  - High-Server: 14 Tage Aufbewahrung
  - Low-Server: 7 Tage Aufbewahrung
- **2 Backup-Jobs:**
  - High & Low getrennt
  - Backup-Befehl über Veeam an vCenter → Snapshot → Backup-Speicherung → Snapshot-Löschung auf Produktivumgebung
- **Tape-Job:**
  - Backups werden nach Sicherung auf Tape übertragen

---

## **Notfallkonzept**
- **Betrieb der IT-Systeme**
- **Dokumentation der IT-Dienste**
- **Notfallreaktion**
- **Wiederherstellungskonzept**
- **Notfallübungen**

---

## **CyberDefense**
- **Überwachung mit PRTG inkl. Pikettorganisation**
- **Externes Security Incident Response Team**
- **Red Team:** 1x jährlich
- **Awareness-Kampagnen:**
  - Phishing-Mails (Portallösung & Schulungen)
  - „User ist das schwächste Glied in der IT-Sicherheit“

---

## **Service Level Agreement (SLA)**
- **Servicezeit:** Mo-Fr 08:00 - 17:00
- **Reaktionszeit:** innerhalb 1 Stunde
- **Proaktive Überwachung:** 06:00 - 22:00

---

## **Notfallreaktionen**
- **Krisenstab via WhatsApp-Gruppe**
- **Telefonliste auf Papier verfügbar**
- **Kommunikationskonzept physisch hinterlegt**

---

## **Wiederherstellungskonzept**
- **Intensive Analysephase**
- **Wiederherstellungsschritte**
- **Wiederanfahrplan:** 11 Tage Full-Restore
- **Worst-Case-Szenario:** Vollständige Verschlüsselung durch Cyberangriff
- **Cyber-Verschlüsselungsschutz**

---

## **Notfallübungen**
- **IT-Audit**
- **Stromausfall eines Rechenzentrums**
- **Datenwiederherstellungstests:**
  - Einzelne Datei
  - Einzelne E-Mail
  - Kompletter Server

Welche speziellen Maßnahmen hat Permapack für die Sicherung von Produktionsdaten implementiert?
→ Werden die Daten von Produktionsanlagen (z. B. Maschinensteuerungen, Prozessdaten) separat gesichert, und falls ja, wie oft und in welchem Umfang?


Welche Backup-Technologie nutzt Permapack zur Sicherung der System- und Anwendungsdaten?
→ Setzt Permapack auf Cloud-basierte Lösungen wie AWS, Azure oder eine eigene Infrastruktur? Welche Backup-Software wird verwendet (z. B. Veeam, Acronis)?
Veem Backup

Wie werden die Backups von Permapack gegen Ransomware-Angriffe geschützt?
→ Gibt es ein "Air-Gapped"-Backup oder andere spezifische Maßnahmen, um sicherzustellen, dass Backups nicht von Ransomware verschlüsselt oder gelöscht werden können?
es giebt anti ransomeware sicherheits systeme

Wie lange werden Backups von Permapack aufbewahrt, und wie wird das Backup-Archiv verwaltet?
→ Gibt es eine Archivierungsstrategie für langfristige Aufbewahrung von Backups (z. B. 7 Jahre gesetzliche Aufbewahrungspflicht), und wie wird die Datenintegrität dieser Backups über einen langen Zeitraum gewährleistet?
10 Jahre

Wie wird das Backup/Restore-Konzept bei Permapack für eine hohe Verfügbarkeit (High Availability) der IT-Systeme während des Wiederherstellungsprozesses sichergestellt?
→ Gibt es redundante Systeme oder eine Notfallinfrastruktur, die es ermöglicht, die Dienste von Permapack bei einem Ausfall innerhalb kürzester Zeit wiederherzustellen?
Picket, Monitoring und 2 RZ für Redundanz


Wie schnell kann Permapack eine Wiederherstellung im Falle eines kompletten Ausfalls der Hauptinfrastruktur durchführen?
→ Gibt es eine genaue Zeitvorgabe für die vollständige Wiederherstellung aller Systeme, z. B. nach einem Rechenzentrumsausfall? Welche Ressourcen (z. B. Cloud, Notfallserver) stehen zur Verfügung, um dies zu ermöglichen?
11 Tage

---

