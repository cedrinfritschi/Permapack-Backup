# Notizen zum Besuch (nur Stichworte)

---

## Infrastruktur

- **390 Clients**
- **88 Server**
  - 5 physikalisch
  - 82 virtuell
- Hauptgebäude: Storage & NAS

---

## Aufbau des Backups

### Software
- **Veeam B&R**
- **Veeam Backup for Microsoft 365** (Einführung: April 2022)

### Microsoft 365 Backup
| Merkmal                  | Wert                  |
|--------------------------|------------------------|
| Lizenzen                 | ~265                   |
| Kosten                   | ~5'500 CHF             |
| Benutzer (User)          | 260                    |
| Postfächer               | 320                    |
| Teams-Gruppen            | 55                     |
| SharePoint Seiten        | 10                     |
| Cloud-Backup-Grösse      | 11 TB                  |
| Source-Daten             | 1.3 TB                 |
| Tägliche Zunahme         | ~15 GB                 |

### Veeam B&R (klassisch)
| Merkmal                  | Wert                  |
|--------------------------|------------------------|
| Socket-Lizenzen          | 8                      |
| Kosten                   | ~10'000 CHF / Jahr     |
| Worker                   | 3 (zur Beschleunigung) |
| Gesicherte Server        | 57                     |
| Source-Daten             | 65 TB                  |
| Aktuelle Backup-Daten    | 115 TB verfügbar       |

---

## Speicherorte der Backups

### RZ1 – NAS02
- **Synology RS3617XS+**
- 16x 4TB SSD
- RAID 6

### RZ2 – NAS01
- **Synology RS4017XS+**
- 28x 8TB HDD
- RAID 5

---

## Tape Backup

- **LTO-8** (Kapazität: ~11 TB pro Tape)
- **HPE 1/8 G2 Tape Autoloader**
  - 1 Slot für Tapewechsel
  - 1 Slot für Reinigungstape

### Medienübersicht
- 1x Cleaning-Tape
- 8x Tagesbänder
- 68x Wochenbänder
  - 5 Tapes pro Woche
- **Lagerung:** Tresor (kühl, trocken, lichtgeschützt)

---

## Restore-Test

### Jahresband-Test
- Immer zu Jahresbeginn
- Nach Test: Dokumentation & 10 Jahre Lagerung

### November-Zufallstest
- Überprüfung:
  - Funktion des Bandes
  - Restore aus der Cloud
  - Dauer
  - Test-VM-Grösse
- Protokollierung aller Tests

---

## Backup-Jobs

| Priorität | Aufbewahrung |
|-----------|---------------|
| High      | 14 Tage       |
| Low       | 7 Tage        |

- Kombination in einem Job möglich

---

## Notfallkonzept (seit Mitte 2020)

### Inhalte
- Betrieb der IT-Systeme
- Dokumentation der IT-Dienste
- Notfallreaktionen
- Wiederherstellungskonzept
- Notfallübungen

---

## Cyber Defense

- **Technische Überwachung:** PRTG inkl. Pikettorganisation
- **Externes Security Incident Response Team**
- **Red Teaming:** 1x pro Jahr
- **Awareness-Kampagnen:** Schulungen & Portallösung

---

## Notfallreaktionen

- Krisenstab: WhatsApp-Gruppe
- Telefonliste: Auf Papier
- Kommunikationskonzept: In Schublade

---

## Wiederherstellungskonzept

- Analysephase
- Restore von NAS oder Tape
- Wiederanfahrplan

---

## Notfallübungen (jährlich)

- IT-Audit
- Stromausfall (Rechenzentrum)
- Datenwiederherstellung:
  - Ein File
  - Ein E-Mail
  - Kompletter Server
