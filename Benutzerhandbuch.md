# Sparverein – Benutzerhandbuch

Dieses Handbuch beschreibt die Bedienung der Sparvereinsverwaltung für Kassiere und Vorstände.

> ⚠️ **Wichtig:** Führen Sie alle Einzahlungen, Auszahlungen und Mitgliederlisten zusätzlich
> **schriftlich in zweifacher Ausführung**. Führen Sie **vor jeder Auszahlung** eine Neuberechnung
> durch und prüfen Sie die Ergebnisse auf Plausibilität. Die Software rechnet, die Verantwortung
> bleibt beim Verein.

---

## 1. Installation und erster Start

Voraussetzung: Windows 10 (ab Version 2004) oder Windows 11. Sonst muss nichts installiert werden.

1. Die ZIP-Datei `Sparvereinsverwaltung-<Version>.zip` herunterladen
   (https://github.com/aortner/Sparvereinsverwaltung/releases).
2. ZIP entpacken und den Ordner an einen festen Ort kopieren (z. B. `C:\Sparverein`), **nicht** in
   „Programme“, da die Datenbank im selben Ordner gespeichert wird und beschreibbar sein muss.
3. `Sparverein.exe` starten. Beim ersten Start wird die Datenbank `sparverein.db` angelegt.
   - Meldet Windows *„Der Computer wurde durch Windows geschützt“*: auf **Weitere Informationen** →
     **Trotzdem ausführen** klicken. Das erscheint, weil das Programm nicht kostenpflichtig signiert ist.
4. Das Programm ist sofort mit der **kostenlosen Lizenz** freigeschaltet (siehe Kapitel 2).
   Weiter mit den Stammdaten.

## 2. Stammdaten und Lizenz einrichten

Menü **Stammdaten**.

### Allgemein

| Feld                     | Bedeutung                                                                 |
|--------------------------|---------------------------------------------------------------------------|
| Lokal (Vereinsname)      | Name des Vereinslokals. **Muss exakt dem Namen in der Lizenz entsprechen.** |
| Adresse, Postleitzahl    | Anschrift des Lokals, erscheint auf den Abrechnungen                       |
| Auszahlung am            | Tag der Jahresauszahlung – bis zu diesem Tag werden Zinsen berechnet       |
| Bank                     | Bank des Vereins, erscheint auf den Abrechnungen                           |
| Lizenzschlüssel          | Den erhaltenen Schlüssel vollständig einfügen                              |

Nach dem Einfügen des Schlüssels auf **Speichern** klicken. Die Lizenz wird sofort geprüft; bei
Erfolg werden Kunde, Ablaufdatum und die maximale Mitgliederzahl angezeigt und alle Menüpunkte freigeschaltet.

Häufige Lizenzmeldungen:

- *„Lizenz ist für einen anderen Verein ausgestellt“* – der Vereinsname im Feld **Lokal** weicht
  vom Namen in der Lizenz ab (Tippfehler, Leerzeichen, Umlaute prüfen).
- *„Lizenz ist … abgelaufen“* – bitte eine Verlängerung anfordern.
- *„Lizenzsignatur ungültig“* – der Schlüssel wurde nicht vollständig oder verändert eingefügt.

### Kostenlose Lizenz bis 31.12.2027

Das Programm ist **bis 31.12.2027 kostenlos**. Eine neue Installation ist dafür schon fertig
eingerichtet: Im Feld **Lokal** steht `Sparverein`, im Feld **Lizenzschlüssel** der kostenlose Schlüssel.
**Das Feld Lokal muss `Sparverein` bleiben**, sonst passt der Schlüssel nicht mehr.

Falls die Felder geändert wurden, `Sparverein` wieder eintragen und diesen Schlüssel in das Feld
**Lizenzschlüssel** kopieren (eine Zeile, vollständig):

```
eyJDdXN0b21lck5hbWUiOiJTcGFydmVyZWluIiwiQ2x1Yk5hbWUiOiJTcGFydmVyZWluIiwiRXhwaXJ5RGF0ZSI6IjIwMjctMTItMzFUMDA6MDA6MDBaIiwiTWF4TWVtYmVycyI6MjAwfQ==.mxcgCf69ULh/tCzkmiD76qb130EIuo9A6+f2iZy/bz/jPhRSAMOkzVcnnjyKj5oRLpFqZAV2IXG0T6wBtbFr0OtZfUpB0sl7efsNwtZJAiLc21yMwrSSALJgx+PI8NpPg9YnWdpDeu2EEuxmtaoiYBYcDkHkIlkHav0rX3YMXy08xaFrqqKrIRlQ4AdOmea59ObVJqIRKuZhWc2ePwoUZ8nFZyM4EqqDDkXQhoOzApGttAmglyyFySc9DKihpBDTzsPGp02rvz9Tip8UDg2Y/EcAyG3brqlT46JR5HK2yr/ZtoYvZBnEmvOFNOtB0hwgCBo9OAMQfvXxwUL/lR2omw==
```

Die kostenlose Lizenz gilt für bis zu **200 Mitglieder**.

**Ab 2028** kostet die Lizenz **0,50 € pro Mitglied und Jahr, höchstens 100 € pro Jahr**.
Für eine Lizenz oder eine neuere Version des Programms einfach an **office@autosteer.cc** wenden.

### Regeln & Finanzen

| Feld                              | Bedeutung                                                                          |
|-----------------------------------|------------------------------------------------------------------------------------|
| Zinssatz (%)                      | Jahreszinssatz, z. B. `1` für 1 %                                                   |
| KESt (%)                          | Kapitalertragsteuer, in Österreich `27,5`                                           |
| Strafe bei Nichteinzahlung (€)    | Betrag, der pro „Straf-Termin“ abgezogen wird                                       |
| Strafe unter € Einzahlung         | Wer an einem Straf-Termin **weniger** als diesen Betrag einzahlt, bekommt die Strafe |
| Essensabzug bei Auszahlung (€)    | Pauschale, die bei der Auszahlung einbehalten wird (z. B. Abschlussessen)           |
| Runden Kommastellen               | 0, 1 oder 2 Nachkommastellen für den Auszahlungsbetrag                              |
| Rundungsart                       | Kaufmännisch oder immer abrunden                                                    |
| Benutzerdefinierter Text          | Wird am Ende jeder Einzelabrechnung gedruckt                                        |

### Aktionen auf der Stammdaten-Seite

- **Auszahlung neu berechnen** – berechnet Zinsen, Strafen, Essensabzug, Rundung und
  Auszahlungsbetrag aller Mitglieder neu. **Nach jeder Änderung an Einzahlungen oder Stammdaten
  ausführen**, sonst zeigen Übersichten, Rangliste und Auszahlung veraltete Werte.
- **Alle Einzahlungen löschen** – z. B. zum Start eines neuen Vereinsjahres. Mitglieder bleiben erhalten.
- **Gefahrenzone → Alle Vereinsdaten löschen** – löscht alle Mitglieder und Einzahlungen.

## 3. Mitglieder

Menü **Mitglieder**.

- **Neues Mitglied anlegen:** Nr., Name, Adresse, PLZ, Geburtsdatum, „Identität festgestellt“.
  Mit „leer anlegen“ wird ein Platzhalter (Name „leer“) für eine freie Nummer erstellt.
- **Bearbeiten / Löschen** über die Schaltflächen in der Tabelle.
- Die Anzahl der Mitglieder ist durch die Lizenz begrenzt.

### Mitgliederliste importieren (CSV)

> ⚠️ Beim Import werden **alle bestehenden Mitglieder und deren Einzahlungen gelöscht** und durch
> die Datei ersetzt. Vorher sichern (Kapitel 9)!

Format: Komma-getrennt, erste Zeile Spaltenüberschriften:

```
Nr,Name,Adresse,Plz,Geb. Datum,IdentitaetFestgestellt
1,Max Muster,Hauptstraße 1,4020,01.02.1970,ja
2,Erika Beispiel,Gasse 5,4020,,nein
```

`Plz`, `Geb. Datum` und `IdentitaetFestgestellt` sind optional (`ja`/`true`/`1` = festgestellt).
Eine Datei aus **Export → Mitglieder als CSV exportieren** hat genau dieses Format.

## 4. Einzahlungen erfassen

Menü **Neue Einzahlung**.

1. **Datum der Einzahlung** wählen (höchstens 10 Tage in der Zukunft). Existieren für dieses Datum
   bereits Einzahlungen, erscheint eine Warnung und das Speichern wird verhindert, um doppelte
   Buchungen zu vermeiden.
2. Optional eine **Bezeichnung** (z. B. „Jänner“) eingeben.
3. **Strafe anwenden** anhaken, wenn an diesem Termin eine Mindesteinzahlung Pflicht ist
   (siehe Stammdaten „Strafe unter € Einzahlung“).
4. Beträge je Mitglied eintragen. Mit **Enter** oder **Pfeil ab/auf** springt man zum nächsten/vorigen
   Mitglied, **Strg+Enter** speichert. Komma und Punkt als Dezimaltrennzeichen sind erlaubt;
   negative Beträge werden abgelehnt.
5. Alternativ **CSV importieren** mit Zeilen `Nr,Betrag` (ohne Kopfzeile, Punkt als Dezimaltrenner),
   z. B. `12,20.50`.
6. **Alle Einzahlungen speichern** – anschließend öffnet sich die Seite **Einzahlungen überprüfen**:
   Dort wird jedes Mitglied einzeln angezeigt und der Betrag kann bei Bedarf korrigiert werden.

Ist „Strafe anwenden“ angehakt oder eine Bezeichnung eingetragen, wird auch für Mitglieder ohne Betrag ein Eintrag über 0 € gespeichert,
damit die Strafe berechnet werden kann.

## 5. Übersichten

- **Einzahlungsübersicht** – Gesamtsummen (Einzahlungen, Zinsen brutto, KESt, Zinsen netto, Strafen, Essensabzug,
  Rundung, Gesamtauszahlung) und je Mitglied alle Einzahlungen. Enthält die druckbaren
  **Einzelabrechnungen** für jedes Mitglied und eine Liste der Mitglieder, bei denen der Essensbeitrag
  nicht abgezogen werden konnte.
- **Übersicht nach Datum** – alle Einzahlungen eines Termins; Datum und Bezeichnung eines Termins
  sowie „Strafe anwenden“ und einzelne Beträge können hier nachträglich korrigiert werden. Mit Münzzähler / Kassenzettel
  zum Abgleich der Kasse. Wird das Datum auf einen Tag geändert, an dem es schon Einzahlungen gibt,
  erscheint eine Warnung; gespeichert wird dann nur nach ausdrücklicher Bestätigung (die Termine
  werden zusammengelegt, Mitglieder können doppelte Einträge bekommen).
- **Rangliste** – Mitglieder nach höchster Einzahlung oder höchsten Zinsen sortiert, mit Zinsen brutto, KESt und netto; druckbar.
- **Mitgliederliste** – druckbare Liste mit Spalte für Unterschrift/Betrag (z. B. für die
  Auszahlung oder Anwesenheit), sortierbar nach Nr. oder Name.
- **Runde Geburtstage** – Mitglieder, die im Jahr der Auszahlung (Stammdaten „Auszahlung am“) 40, 45, 50, … Jahre alt werden, nach Datum sortiert.

## 6. Auszahlung

1. **Stammdaten → „Auszahlung am“** prüfen und **Auszahlung neu berechnen** ausführen.
2. Menü **Auszahlung**: zeigt die Gesamtübersicht, den **Gesamtbedarf an Scheinen und Münzen**
   für die Bank und die Stückelung pro Mitglied.
3. **Drucken** erzeugt die Auszahlungsliste mit Spalte „Identität geprüft“.

So wird der Auszahlungsbetrag berechnet:

```
  Summe der Einzahlungen
+ Zinsen netto   (Betrag × Zinssatz × Tage bis zur Auszahlung / 365, abzüglich KESt)
− Strafen        (höchstens bis das Guthaben 0 ist)
− Essensabzug    (nur wenn genug Guthaben vorhanden)
± Rundung
= Auszahlung
```

## 7. Jahresabrechnung

Menü **Abrechnung**.

- **Vereinsabrechnung:** Summe der Einzahlungen, Zinsen brutto abzüglich KESt, Strafen, Essensbeitrag und Rundung
  ergeben die Summe der Auszahlungen.
- **Zinsvergleich:** tatsächlich von der Bank erhaltene Zinsen eintragen – daraus ergibt sich der
  Zinsgewinn bzw. -verlust des Vereins.
- **Endabrechnung Verein:** Zinsdifferenz + Strafen ± Rundung + bis zu 5 weitere Einnahmen −
  bis zu 5 weitere Ausgaben = **Gewinn für den Verein**.

Alle Eingaben auf dieser Seite werden automatisch (ca. 1 Sekunde nach der Eingabe) in der
Vereinsdatenbank gespeichert. **Drucken** gibt die Abrechnung aus.

## 8. Export

- **Mitglieder als CSV exportieren** – `mitglieder.csv`, kann direkt wieder importiert werden.
- **Alle Einzahlungen als ZIP exportieren** – je Einzahlungstermin eine CSV-Datei
  (`Bezeichnung_JJJJ-MM-TT.csv`) mit `Nr,Betrag`, die auf der Seite **Neue Einzahlung** wieder
  importiert werden kann.

## 9. Datensicherung

Alle Daten stehen in der Datei **`sparverein.db`** im Programmordner.

- Zum Sichern das Programm schließen und die Datei z. B. auf einen USB-Stick kopieren.
- Zum Wiederherstellen die gesicherte Datei zurück in den Programmordner kopieren.
- Empfehlung: nach jedem Einzahlungstermin und vor jeder Auszahlung sichern.

### Update auf eine neue Version

Das Programm sucht **nie von selbst** nach Updates. Zum Prüfen:

1. Auf der **Startseite** (Home) auf **„Nach Updates suchen“** klicken. Dabei wird kurz bei GitHub
   nachgefragt; es werden keine Vereinsdaten übertragen.
2. Gibt es eine neue Version, erscheint ein Hinweis mit Link **„Was ist neu?“**.
3. **„Jetzt aktualisieren“** klicken und die Rückfrage bestätigen. Das Programm
   - sichert die Datenbank als `sparverein_vor_update_<alte Version>_<Datum>.db` im Programmordner,
   - lädt die neue Version herunter, beendet sich, ersetzt die Programmdateien und startet neu.

Die Vereinsdaten in `sparverein.db` bleiben erhalten; die Datenbank wird beim Start automatisch
auf den neuen Stand gebracht. Die Versionsnummer steht auf der Startseite.

Ohne Internet oder bei Version 1.0.0: die neue ZIP von
https://github.com/aortner/Sparvereinsverwaltung/releases herunterladen, entpacken und
`Sparverein.exe` sowie den Ordner `wwwroot` über die alten kopieren – `sparverein.db` behalten.

## 10. Ablauf eines Vereinsjahres (Kurzfassung)

1. Stammdaten prüfen, Mitglieder anlegen oder importieren.
2. An jedem Termin: **Neue Einzahlung** erfassen → überprüfen → sichern.
3. Vor der Auszahlung: **Auszahlung am** setzen → **Auszahlung neu berechnen** → Übersichten prüfen.
4. **Auszahlung** drucken, Geld bei der Bank beheben, auszahlen, Identität abhaken.
5. **Abrechnung** mit den Bankzinsen und weiteren Posten abschließen und drucken.
6. Datenbank sichern, dann für das neue Jahr **Alle Einzahlungen löschen**.

## Support

Lizenzen, Verlängerungen und Support: **office@autosteer.cc**

Impressum, Datenschutzerklärung, Nutzungsbedingungen (EULA) und Lizenzen der verwendeten Komponenten sind über die Fußzeile jeder Seite erreichbar.
