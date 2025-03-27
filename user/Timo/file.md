# Permapack
## IT Rollen
Infrastruktur\
Enterprise Infastructure Planing\
Supporter\
Lernende\

## Datensicherung
### Übersicht Infrastruktur
400 Clients
gröstenteils Clients
88 Server (82 virtuell/ 5 physikalisch)
3 Rechenzentren
Veeam Backup & Replication
Veem M365 265 Lizenzen 5500 CHF
260 User
320 Postfächer
55 Teams Gruppen
10 SharePoint Seiten
Backup 11 TB
Produktiv 1.3 TB Source-Daten
+15 GB Pro Tag
Backup auf Produktiven Storage auf einer VM

### Veem Backup & Replication
8 Socket Lizenzen 
10'ooo CHF im Jahr
3 Worker um backups zu beschleunigen
Jeder ESx hat einen eigenen Worker
Sichert 57 Server 65 TB an Source-Daten
Altes ERP ist nicht mehr sicherungsrelevant
Aktuell 115 TB an Backups direkt auf einem NAS verfügbar
Server High und Low
High Server 14 Snapshots
Low Server 7 Snapshots
Backüp läuft durchgehend
Syntetic full backup es wird alle woche ein fullbackup berechnet
Application Aware Processing
Kpien werden bis zu einem jahr in einem copy job geschpeichert
1x Nas 16x 4 TB SSD
1x Nas 28x 8TB HDD
LTO 9 11 TB da veam schon die datenkompriemiert hat nicht 30 TB
HPE Tape Autoloader
1 Cleaningtape
8 Tagesbänder
68 Wochenbänder 
Sie Tapes werden in einen Tresor Gelagert
Wochenband nach 2-3 monate
Tagesbänder 1-2 Woche
Monatsbänder 3-6 Monate
Jahresband Test zu Beginn 10 Jahre
Im November Zufallstest
Funktion des Bandes
Cloud Restore
Dauer
Grösse der Test-VM

### Backup Jobs
Tägliche sicherung 
high 14 Tage
und low 7 Tage
2 Backup jobs wegen high und Low
Tape job wenn die backups gelesen wurde werden sie auf Tape geschrieben
die jobs veem geht hin sendet befehl an vceneter vcenter erstellt snapshot und wird auf backup gespielt snapshot wird auf prod umgebung gelöscht

### Notfallkonzept
Betrieb It-System
Dokumentation der IT-Dienste
Notfallreaktion
Wiederherstellungskonzept
Notfallübung

### CyberDefense
überwachung mit PRTG inkl. Pikettorganisation
externe Security Incident Respose Team
Red Team wird nur einmal pro Jahr eingesetzt
Awareness Kampagnen Phishing Mails (Portallösung und Schulungen)
User ist das Schwächste glied in der IT-Sicherheit

### Service Level Agreement
Servicezeit:
Mo-Fr 08:00 - 17:00
Reaktionszeit
innert 1 Stunde
Proaktive überwachung: wärhrend 06:-22 Uhr

### Notfallrektionen
Kriesenstab vie Whatsapp-Gruppe
Telefonliste auf Papier
Kommunikationskonzept in Schublade

###  Wiederherstellungskonzept
Intense Analysephase
Wiederherstellung
Wiederanfahrplan 11 Tagen full Restore
Worstcase Alles verschlüsselt
Cyberverschlüsselung

### Notfallübungen
IT-Audit
Stromausfall einese Rechenzentrums
Datenwiederherstellung (ein File, ein E-Mail und ein Server komplett)









