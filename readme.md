# Dokumentation (Entwurf)

## Motivation und Ziel
Besprechungsserien gehören für viele zum Alltag dazu. Der Zeitaufwand für die Administration verfielfacht sich bei manueller Protokollführung, das Nachhalten von Aufgaben und formatieren von E-Mails, was ich persönlich als nicht mehr zeitgemäß empfinde. Dieses Tool baut auf folgender Grundlage auf:

- Das Besprechungsprotokoll wird für alle Sichtbar während der Besprechung geführt und kann danach sofort verteilt werden.
- Jedes besprochene Thema erhält eine eindeutige Besprechungspunktnummer (ID) und ist damit Rückverfolgbar.
- Es gibt nur die Typen von Besprechungspunkten:
     Agenda: Vorbereiteter Punkt. Wird im Verlauf der Besprechung zu einem der folgenden drei Punkten:
     Info: Information ohne Handlungsbedarf. Diese Punkte sind in der folgenden Besprechung inaktiv.
     Aufgabe: Konkrete Aufgabe mit Zieltermin und eine verantwortliche Person. Diese Punkte sind bis zur Erledigung aktiv (sichtbar).
     Entscheidung: Beschlüsse die eine Handlungsgrundlage darstellen können und daher hervorzuheben sind. Bei Bedarf können diese im Protokoll immer wieder aufgeführt werden.
- Jeder Besprechungspunkt sollte einer Kategorie zugeordnet werden.
- Darüber hinaus kann jeder Besprechungspunkt einem Projekt zugeordnet werden (Multiprojektmodus).

---
## Über das Projekt

### Hauptfunktionen
Das Tool ist in vier logische Phasen unterteilt, die den Nutzer intuitiv durch das Meeting leiten:

 Vorbereitung:
     Verwaltung von regulärer Agenda (Routine-Themen) und einmaligen Agendapunkten (aktuelle Highlights, Ereignisse usw).
     Automatisierte Einladungstexte und berechnete Folgetermine.
 Durchführung:
     Keyword-Erkennung: Automatischer Typ-Wechsel während des Tippens (z. B. erkennt das System `Aufgabe:` und blendet sofort die Termin- und Verantwortlichen-Felder ein).
     Schnelleingabe-Menüs: Schnelles auflisten von Teilnehmern oder Referenzieren von alten Punkten per Tastatur-Shortcut.
     Timer:  Zeiterfassung und Pausenmanagement zur Einhaltung des Zeitrahmens.
 Reibungsloser Abschluss:
     Anwesenheits-Historie: Automatische Übernahme des Protokollführers und Dokumentation der Teilnehmer.
     Nachzügler-Check: Schnelle Erfassung von Personen, die später zum Termin gestoßen sind.
 Automatisierter Export & Kommunikation:
     Multiformat-Export: Ein-Klick-Generierung von HTML-Protokollen, CSV-Listen und JSON-Backups.
     Kommunikations-Vorlagen: Fertig formatierte Texte für Messenger oder E-Mail, inklusive dynamischer Platzhalter und optional integrierter Feedback-Links (an den Moderator).

### Technische Infos
 Technologie-Stack: Pures HTML5, CSS3 und Vanilla JavaScript. Keine externen Abhängigkeiten oder Frameworks (kein React/Angular), was die Langzeit-Kompatibilität sichert.
 Datenspeicherung (IndexedDB): Alle Daten werden verschlüsselt in der lokalen Datenbank deines Browsers gespeichert. Es verlassen zu keinem Zeitpunkt Daten dein lokales System.

### ⚖️ Lizenz & Rechtliches
Dieses Projekt steht unter der MIT-Lizenz. Das bedeutet: Du darfst es frei verwenden, modifizieren und teilen, solange der ursprüngliche Copyright-Hinweis erhalten bleibt. Die Nutzung erfolgt auf eigene Gefahr (siehe Info-Dialog im Tool).

Das freut mich! Hier ist das nächste Kapitel für deine README, das den Fokus auf die praktische Inbetriebnahme und die logischen Abläufe legt.

---
## Schnellstart

### Installation & Voraussetzungen
Da das Tool als Single-Page-Application (SPA) konzipiert ist, gestaltet sich die "Installation" denkbar einfach:

1.  Speichere die Datei `index.html` in einem lokalen Ordner auf deinem Rechner oder nutze diese Webseite.
2.  Öffne die Datei mit einem modernen Webbrowser (Edge, Chrome, Firefox).
3.  Wichtig: Da das Tool die `IndexedDB`-Technologie nutzt, stelle sicher, dass du den Browser nicht im "Privaten Modus" (Inkognito) ausführst, da die Daten sonst beim Schließen des Tabs gelöscht werden.

### Die erste Besprechung starten
Um sofort produktiv zu werden, empfiehlt sich dieser Ablauf:

1.  Stammdaten pflegen: Gehe in den Bereich Organisation und lege Teilnehmer, Orte und Kategorien fest.
2.  Einstellungen: Hinterlege deinen Organisationnamen und lade dein Logo hoch.
3.  Agenda definieren: Erfasse unter Agenda verwalten deine Routine-Punkte.
4.  Meeting starten: Klicke im Startmenü auf Besprechung starten. Das System berechnet automatisch die neue Protokollnummer (z. B. 200, 300, etc.) und führt dich zur Anwesenheitsprüfung.

---
## Arbeitsbereiche & Module

### Dashboard & Navigation
Das Tool ist in einer flachen Hierarchie aufgebaut, um schnelle Wechsel während einer Diskussion zu ermöglichen:
 Startmenü: Zentrale Schaltstelle für Vorbereitung und Stammdaten.
 Eingabefenster: Der "Maschinenraum". Hier findet die Keyword-Erkennung statt.
 Listenansicht: Ein interaktives Dashboard aller aktiven und archivierten Punkte mit umfangreichen Filteroptionen.

### Meeting-Modus & Keyword-Erkennung
Die Eingabe ist auf Geschwindigkeit getrimmt. Das System reagiert live auf deine Eingaben:
 Automatische Typisierung: Tippst du Begriffe wie `Aufgabe:` oder `Action:`, schaltet das UI sofort um und blendet das Feld für den Verantwortlichen sowie das Zieldatum ein.
 Referenzierung (#): Tippe das Raute-Symbol, um eine Liste alter Besprechungspunkte aufzurufen und diese direkt zu verlinken.
 Teilnehmer-Ping (+): Tippe ein Plus-Zeichen, um Teilnehmernamen blitzschnell in den Text einzufügen.

### Teilnehmer- & Stammdatenverwaltung
Hier verwaltest du das "Personal" deiner Besprechungen. 
 Aktiv-Status: Teilnehmer können deaktiviert werden, ohne ihre Historie in alten Protokollen zu verlieren.
 Stille Mitleser: Personen, die nicht anwesend sind, aber das Protokoll automatisiert erhalten sollen.
 Namenszusätze: In den Einstellungen kannst du wählen, ob hinter dem Namen die Firma oder die Funktion in Klammern angezeigt werden soll.

Hier ist der Entwurf für das vierte Kapitel, das die Schnittstelle zwischen deiner lokalen Datenbank und der Außenwelt (E-Mail, Teams, Archiv) beschreibt.

---
## Automatisierung & Export

### Protokoll-Exporte (HTML, JSON, CSV)
Das Tool bietet drei verschiedene Export-Wege, um unterschiedliche Anforderungen abzudecken:
 HTML-Protokoll (Druckansicht): Generiert ein formatiertes, druckreifes Protokoll im Corporate Design inklusive Logo. Ideal zum Speichern als PDF oder zum direkten Ausdrucken.
 CSV-Export: Exportiert alle Punkte einer Sitzung oder gefilterte Ansichten (z. B. nur offene Aufgaben) für eine Tabellenkalkulation.
 JSON-Backup: Ermöglicht den Export der gesamten Datenbank. Dies dient der langfristigen Archivierung oder dem Umzug der Daten auf einen anderen Rechner.

### Textvorlagen & Platzhalter
Die Kommunikation wird durch ein Template-System gesteuert. Du kannst eigene Vorlagen für Einladungen, Protokoll-Zusammenfassungen oder Aufgaben-Reminder erstellen. Das System ersetzt dabei automatisch folgende Platzhalter durch Echtzeit-Daten:
 `{Titel}`, `{Datum}`, `{Ort}`: Basisdaten der Besprechung.
 `{Agenda}`: Kombinierte Liste aus einmaligen und regelmäßigen Punkten.
 `{Aufgaben}`: Tabellarische oder listenförmige Aufbereitung der To-dos.
 `{Feedback}`: Erzeugt dynamische Mailto-Links, mit denen Teilnehmer mit einem Klick strukturiertes Feedback an den Moderator senden können.
 `{Ablageort}`: Verlinkt automatisch auf den im System hinterlegten Netzwerkpfad oder Cloud-Ordner.

---
## Konfiguration & Personalisierung

### System-Einstellungen
In diesem Bereich passt du das Tool an deine Arbeitsweise an:
 Rhythmus & Fristen: Definiere, nach wie vielen Tagen Aufgaben archiviert werden sollen und wie weit in die Zukunft die automatische Terminberechnung greifen soll.
 Corporate Identity: Hinterlege dein Firmenlogo (als Base64-String) und den Organisationsnamen für alle Exporte.

### Design-Modi (Dark Mode)
Um die Augen bei langen Meetings zu schonen, verfügt das Tool über einen intelligenten Dark Mode. Dieser kann manuell umgeschaltet werden oder passt sich (je nach Browsereinstellung) automatisch an die Systemeinstellungen deines Betriebssystems an.

Hier ist das abschließende Kapitel zur Sicherheit und Technik, gefolgt von den Hinweisen für Entwickler. Damit ist deine README komplett und bereit für den Einsatz!

---
## Datenschutz & Sicherheit

### Lokale Speicherung (IndexedDB)
Alle Informationen, die du eingibst – von Teilnehmernamen bis hin zu vertraulichen Beschlussfassungen – werden ausschließlich in der IndexedDB deines Browsers gespeichert. 
 Kein Server: Es gibt kein Backend und keine Datenbank in der Cloud.
 Kein Tracking: Das Tool sendet keine Telemetriedaten oder Analysen nach außen.
 Vollständige Kontrolle: Deine Daten verlassen deinen Rechner nur dann, wenn du explizit einen Export (HTML, CSV oder JSON) teilst.

### Backup & Wiederherstellung
Da die Daten an den Browser gebunden sind, ist ein regelmäßiges Backup essenziell. Das Tool bietet hierfür eine dedizierte Funktion in den Einstellungen, um den gesamten Datenbestand als verschlüsselt lesbare JSON-Datei zu sichern. Dies schützt vor Datenverlust bei Systemreinigungen oder Browser-Resets.

---
## Entwickler-Hinweise

### Projektstruktur
Das Tool ist als monolithische HTML-Datei aufgebaut. Dies erleichtert die Verteilung ("Einfach die Datei verschicken") und sorgt für maximale Offline-Stabilität. 
 CSS: Intern im `<style>`-Block (Modular aufgebaut nach Ansichten).
 JavaScript: Funktional programmiert, unterteilt in Module für UI-Logik, Datenverarbeitung und Export-Funktionen.
 Datenmodell: Nutzt ein zentrales Array `arrProtokollDaten` für alle Protokolleinträge.

### Triggerwörter
Die Keyword-Erkennung in der Texteingabe reagiert aktuell auf folgende Begriffe (erweiterbar in `ueberwacheTexteingabe`):
 Aufgabe: `aufgabe:`, `task:`, `todo:`, `action:`, `auftrag:`, `erledigen:`
 Entscheidung: `entscheidung:`, `decision:`, `beschluss:`, `fix:`, `ergebnis:`

---
## Lizenz & Rechtliches

Dieses Projekt ist unter der MIT-Lizenz lizenziert.

Die Software wird "wie besehen" (as is) zur Verfügung gestellt, ohne jegliche ausdrückliche oder stillschweigende Gewährleistung. In keinem Fall sind die Autoren oder Urheberrechtshinhaber für Ansprüche, Schäden oder andere Haftungen haftbar, die sich aus der Software oder der Nutzung der Software ergeben.
