# allgemeines
5 Häuser
320 MA
30% produ
70 % handel
25 Lernende
Druckerei 10 diverse farben
Laminat tuben, ohne inhalt
Ettiketen
versand
Transport Sicherung-> stretchfolien
Obst und Gemüse
Getränke(sixpack)
verbundfolien
18000 artikel
bau-produkte
industrie produkte->uhr -> schutzfolie
retail- Garten

# Backup konzept

## infrastruktur
390 CLints ->
88 Server (82 Virtuell / Physisch) -> physisch nur für vm
3 Rechen zentren
tape library 
veeam
veeam backup office 365
-> 265 lizenzen -> 5500 CHF pro jahr
- 260 user
- 320 Postfächer (shared postfächer)
- 55 teams gruppen
- 10 sharepoint
11 TB 
1.3 TB source
15 GB pro tag
esx auf produktiven storage server




## aufbau backup

8 Socket Lizenzen
- ~10000 CHF pro jahr
- 3 Worker
sichert
- 57 server -> nicht 88 weil -> citrix server geklont
- 66 TB source data
aktuall 115 TB cloudbackup
server backup zeitrstrahl
backup high -> 23:00 -> da erp sachen noch um 21:00 laufen
backup low -> 20:00
copy jobs läuft durchgehend
alle tagen das gleiche backup
freitag systetic full backup -> speziell aber eigentlich einfaches fullbackup
kompriieren
im copy job daten bis zu einem jahr
daten gehen hier hin:
- Syno NAS 16x 4TB SSD -> RZ 1
- Syno NAS 28x 8 TB HDD -> RZ 2
LTO 8 Tapes 11 - 30 TB -> druch veeam nur 11 TB
Tape loader bis zu 8 Tapes
cleaning tape und input output slot und reste normale tapes
68 Wochenbänder -> per zufall ein monats und zufall jahresband
Veeam ist virtuell
veeam backup sichert den physikalischen server selber auch noch
zurück vom tresor:
wocehn band nach 2 mönaten
tag 1-2 wochen
monats alle 6 monate
jahres kommt nicht zurück
jahres band wird nach beginn des jahres getestet
november zufalltest:
- funtioni bandes
- cloud restor
- dauer
- grösste der Test-VM
Tests werden protokolliert
## demo restore
### Jobs
5 Jobs insgesamt
## Notfallkontept
mitte 2020 offizielle dokument
inhalte:
- Betrieb
	 - Cyber defense
	 - eigene überwachung (PRTG)
	 - externes securtity incident response team
	 - RED Team(externes team) wird nur einmal im jahr eingesetzt -> audit
	 - awarenes Kampagne
	Service zeit 8:00 - 17:00
	Reaktionszeit innert 1 Stunde
- Dokumentation it dienste
	- server Übersicht
- notfallreatkionen
	- krisenstab Whatsapp gruppe
	- telefonliste papier
	- kommunikationskonzept in schublade
- Widerherstellungs konzept
	- intensive Analysephase
	- Widerherstellung ab NAS oder Bandlaufwrek
	- Wiederanfahrplan -> wie lange was geht zum wiederherstellen -> nach 11 Tagen würde alles wieder laufen (clients und server)
- Notfall Übungen
	- IT-Audit
	- Stromausfall eines Rechenzentrums
	- Datenwiederherstellung (File, Email, Server komplett)
	

