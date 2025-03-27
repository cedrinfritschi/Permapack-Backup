### Permapack

#### Abteilung
Non Food 
Food 
Cosmetic - Etiketten, Tubenlaminat

#### Übersicht der Infrastruktur
- 390 Clients Computer, Notebooks, All in one
- 88 Server (82 virtuell/ 5 echte)

#### Aufbau Backup
##### Veeam + Cloud

- Veeam 365
	- 265 Lizenzen
	- 5500 CHF pro Jahr
	- Sichert: 260 User, 320 Postfächer, 55 Teams Gruppen, 10 Sharepoint Seiten
	- 1.3 TB Source-Daten
	- Zunahme 15 GB täglich

Im produktiven Storage absichtlich

- Veeam Backup Replication
	- 8 Socket Lizenzen 4 ESXI 2 Prozessor 8 Lizenzen
	- 10 000 CHF pro Jahr
	- 3 Worker (Backup beschleunigen, Daten so komprimieren dass sie schneller durchs internet gehen)
	- 57 Server (Citrix Master Server gebackupt, Slave ist automatisch dabei, Alte System mit alten daten)
	- 65 TB an Source-Daten
	- Aktuell 115TB an Backups sofort verfügbar

- All woche 1 Full Backup, VMs bekommen nichts mit, Full Full dauert 2 bis 3 Tage übers Wochenende zu lang
- Bis zu einem Jahr verfügbar

##### Aufbau des Storage
- RZ 1- NAS02
- Synology RS3617xs+
- 16x 4 TB SSD

- RZ 2 - NAS01
- Synology RS4017xs+
- 28x 8 TB HDD

##### RAIDS
- SSD NAS RAID 6
- HDD NAS RAID 5


##### Tapes
- LTO 8 a ~11 TB
- HPE 1/8 G2 Tape Autoloader
- 1 Cleaningtape
- 8 Tagesbänder
- 68 Wochenbänder

##### Restore Test
- Jahresband zu beginn testen
- Im November Zufalsstest
	- Funktion des Bandes
	- Cloud und Restore
	- Dauer
	- Grösse der Test-VM

Server LOW 20 Uhr bis 20:30
Server HIGH 23 UHR bis 0 oder halb 0:30

#### Notfallkonzept

- seit Mitte 2020 offizieles Dokument
- Inhalt
	- Betrieb der IT-Systeme
	- Dokumentation der IT Dienste
	- Netfallreaktion
	- Wiederherstellungskonzept
	- Notfalübungen

##### Betrieb der IT-Systeme
- Cyber Defense
	- eigene technische Überwachung der Systeme (PRTG) inkl. Pikettorganisation
	- exterenes Security Incident Response Team
	- Red Team wird nur einmal pro Jahr eingesetzt
	- Awarness Kampagnen (Portallösung und Schulungen)

##### Service Level Agreement
- Servicezeit: 8-17 Uhr
- Reaktionszeit: innert 1 Stunde Während Werktage 6 bis 22, Wochenende innert 8 Stunden

##### Notfallreaktion
- Krisenstab via Whatsapp-Gruppe
- Telefonliste auf Papier
- Kommunikationskonzept in Schublade

##### Wiederherstellungskonzept
- Intensive Analysephase
- Wiederherstellung ab NAS oder ab Bandlaufwerk
- Wiederanfahrplan

nach 3 Tagen können 10 Arbeiten von 320 
nach 11 Tagen können alle Arbeiten

Verbesserung: schneller machen

##### Notfallübungen
- IT-Audit
- Stromausfall eines Rechenzentrums
- Datenwiederherstellung (ein Fil, ein E-Mail und ein Server komplett)

##### Datenarchivierung
- Jahresbänder im Tresor 10 Jahre aufbewahren

##### Ausfallsicherheit
- Tresor: Lichtgeschütz, trocken, kühl

Wo welches ist, Veeam übernimmt einen Teil, mobile wereden protokoliert wenn es benutzt worden ist

2 Leute sind für Backup von 8

##### Notstromkonzept

Alle Server USV mit 20 Minuten, nach 20 Minuten alle herunterfahren


Hochwasser 3. Etage oben
Verbrennen: 2. Gebäude
