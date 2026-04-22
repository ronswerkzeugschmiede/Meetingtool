# 📊 Meeting-Analytics Dokumentation

Das Dashboard wertet automatisch alle abgeschlossenen Besprechungen aus deiner `arrAnwesenheitsHistorie` und die Inhalte aus `arrProtokollDaten` aus.

## 🕒 Zeit-Disziplin & Effizienz
Diese Karten zeigen, wie gut die Zeitplanung eingehalten wird.

* **Termintreue (Soll/Ist)**: Vergleicht die `datIstStartZeit` und `datIstEndeZeit` mit den Vorgaben aus den Stammdaten.
    * 😇 **Grün**: Pünktlicher Start / Frühes Ende.
    * 😐 **Gelb**: Akzeptable Abweichung (bis 15 Min.).
    * 😫 **Rot**: Deutliche Überziehung oder Verspätung.
* **📊 Effizienz**: Zeigt die durchschnittliche Anzahl der Punkte pro Meeting und die Zeitkosten pro Punkt an.
    * *Berechnung:* `Gesamtzeit / Anzahl aller Protokollpunkte`.
* **⏱ Erledigungs-Dauer**: Die durchschnittliche "Lebenszeit" einer Aufgabe.
    * *Berechnung:* Differenz zwischen Erstellungsdatum (Besprechungs-Nr.) und `datErledigungsdatum`.

---

## 👥 Teilnehmer-Dynamik
Hier wird das soziale Gefüge und die Verbindlichkeit der Serie analysiert.

* **🏆 Kern-Team**: Die Personen mit der höchsten Anwesenheitsquote (nahe 100 %). Dies sind die verlässlichsten Stützen deiner Besprechungsserie.
* **👻 Ghosting**: Personen, die oft auf dem Verteiler stehen (`arrAbwesende`), aber selten teilnehmen (Quote unter 50 %).
    * *Nutzen:* Hilft zu entscheiden, ob der Teilnehmerkreis verkleinert werden kann.
* **✅ Erledigungs-Quote**: Das Verhältnis von offenen zu erledigten Aufgaben.
    * *Ziel:* Eine Quote > 80 % signalisiert einen gesunden Workflow.

---

## 🔨 Aufgaben & Inhalte
Dieser Bereich zeigt, wer die Last trägt und wie produktiv die Treffen sind.

* **🔨 Aufgaben-König**: Die Person, die im Feld `strName` am häufigsten als Zuständige für den Typ **Aufgabe** eingetragen ist.
* **💡 Mix (I/A/E)**: Die Verteilung der Protokollpunkte nach Typ:
    * **I** = Info (Wissensaustausch)
    * **A** = Aufgabe (Operatives Tun)
    * **E** = Entscheidung (Strategischer Fortschritt)
    * *Tipp:* Ein hoher Anteil an Entscheidungen spricht für sehr effektive Meetings.

---

## ⚖️ Das dynamische Fazit
Basierend auf der **Erledigungs-Quote** gibt dir das Tool ein direktes Feedback:

* 🚀 **Extrem produktiv!**: Fast alle Aufgaben werden zeitnah abgearbeitet.
* ⚖️ **Stabiler Workflow**: Die Erledigung hält sich die Waage mit neuen Aufgaben.
* ⚠️ **Aufgaben-Stau!**: Es kommen mehr Aufgaben hinzu, als abgearbeitet werden.

---

> **Hinweis zur Datenbasis**: Alle Statistiken werden in Echtzeit berechnet, sobald du die Anwesenheits-Historie öffnest. Manuelle Änderungen an den Zeiten oder Teilnehmerlisten in der Tabelle wirken sich sofort auf die Analytics aus.