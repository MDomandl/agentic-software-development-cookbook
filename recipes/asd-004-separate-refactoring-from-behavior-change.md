# ASD-004 – Separate Refactoring from Behavior Change

## Problem

Ein Agent verändert gleichzeitig die technische Struktur und das fachliche Verhalten.

Zum Beispiel:

* Funktionen werden extrahiert
* Klassen werden aufgeteilt
* Dateien werden verschoben
* Namen werden geändert
* zusätzlich wird neue Fachlogik eingebaut

Wenn sich danach ein Ergebnis verändert, ist schwer festzustellen, wodurch die Änderung verursacht wurde.

## Grundsatz

Refactoring und fachliche Verhaltensänderung sollten in getrennten, einzeln prüfbaren Arbeitsschritten erfolgen.

Beim Refactoring gilt:

> Die Struktur darf sich ändern. Das beobachtbare Verhalten soll gleich bleiben.

Bei einer fachlichen Änderung gilt:

> Das Verhalten wird bewusst geändert. Die technische Struktur bleibt möglichst stabil.

## Wann anwenden?

Dieses Recipe ist besonders wichtig, wenn:

* bestehende Fachlogik umgebaut werden soll
* eine neue Funktion eine strukturelle Vorbereitung benötigt
* Tests während einer Änderung stark angepasst werden müssen
* ein Diff sowohl Umbenennungen als auch neue Logik enthält
* Fehler später eindeutig zugeordnet werden müssen
* Änderungen einzeln reviewbar oder revertierbar bleiben sollen

## Vorgehen

### 1. Aktuelles Verhalten absichern

Vor einem Refactoring sollte das relevante Verhalten ausreichend verstanden und möglichst durch Tests oder Vergleichsartefakte abgesichert sein.

Siehe:

* `ASD-001 – Current Behavior First`

### 2. Änderungsarten unterscheiden

Vor Beginn wird geklärt, welche Teile der Aufgabe zu welcher Kategorie gehören.

Typisches Refactoring:

* Funktion extrahieren
* Klasse aufteilen
* Code verschieben
* Namen verbessern
* Abhängigkeiten klarer strukturieren
* Duplikate entfernen

Typische Verhaltensänderung:

* neue fachliche Regel
* geänderte Berechnung
* neue Validierung
* veränderte Ausgabe
* neue Fehlerbehandlung
* zusätzliche unterstützte Eingabe

### 3. Refactoring separat durchführen

Im Refactoring-Schritt darf kein beabsichtigtes fachliches Verhalten geändert werden.

Der Agent soll:

* die Änderung eng begrenzen
* keine neue Fachlogik ergänzen
* vorhandene Tests möglichst erhalten
* Tests nur wegen der neuen Struktur anpassen
* relevante Prüfungen ausführen
* unerwartete Verhaltensänderungen melden

### 4. Refactoring prüfen und abschließen

Vor der fachlichen Änderung wird geprüft:

* Sind nur strukturelle Änderungen enthalten?
* Bleiben Ein- und Ausgaben gleich?
* Sind Tests weiterhin grün?
* Wurden keine neuen Sonderfälle eingeführt?
* Ist der Diff verständlich?

Das Refactoring sollte einen eigenen nachvollziehbaren Zwischenstand oder Commit bilden.

### 5. Fachliche Änderung separat umsetzen

Erst danach wird das gewünschte Verhalten geändert.

In diesem Schritt gilt:

* kein zusätzliches Aufräumen
* keine weiteren Datei- oder Klassenverschiebungen
* keine unnötigen Umbenennungen
* Tests gezielt für das neue Verhalten ergänzen
* erwartete Verhaltensänderung ausdrücklich dokumentieren

## Geeigneter Agentenauftrag für das Refactoring

```text
Führe ausschließlich das notwendige Refactoring durch.

Ziel:
Die bestehende Struktur für die spätere Änderung vorzubereiten.

Grenzen:
- kein fachliches Verhalten ändern
- keine neue Funktionalität ergänzen
- keine nicht notwendigen Dateien ändern
- Tests nur anpassen, wenn die Strukturänderung dies erfordert
- keine Folgeaufgabe automatisch umsetzen

Prüfe anschließend:
- welche Dateien geändert wurden
- ob Ein- und Ausgaben unverändert bleiben
- welche Tests ausgeführt wurden
- ob es Hinweise auf unbeabsichtigte Verhaltensänderungen gibt
```

## Geeigneter Folgeauftrag für die Verhaltensänderung

```text
Setze jetzt ausschließlich die vereinbarte fachliche Verhaltensänderung um.

Die vorbereitete Struktur soll nicht weiter refactort werden.

Grenzen:
- keine zusätzlichen Umbenennungen
- keine Datei- oder Klassenverschiebungen
- kein allgemeines Aufräumen
- nur für das neue Verhalten notwendige Tests ergänzen

Dokumentiere anschließend:
- welches Verhalten sich bewusst geändert hat
- welche Fälle unverändert bleiben
- wie die Änderung geprüft wurde
```

## Anti-Patterns

### Refactoring als Nebenprodukt

Der Agent ergänzt eine kleine Funktion und baut dabei angrenzende Bereiche umfassend um.

Risiko:

Der Diff wird unnötig groß und schwer prüfbar.

### Verhaltensänderung im Refactoring verstecken

Bei einer Strukturänderung wird eine bestehende Regel „gleich mit korrigiert“.

Risiko:

Die fachliche Änderung ist weder klar beauftragt noch separat getestet.

### Tests vollständig neu schreiben

Der Agent ersetzt beim Refactoring große Teile der Tests.

Risiko:

Die neue Teststruktur bestätigt möglicherweise nicht mehr dasselbe Verhalten.

### Strukturänderung im Feature-Schritt

Während einer fachlichen Änderung werden zusätzliche Klassen, Schichten oder Abstraktionen eingeführt.

Risiko:

Fehler lassen sich nicht eindeutig der Fachlogik oder der neuen Struktur zuordnen.

## Ergebnis

Nach Anwendung dieses Recipes entstehen getrennte, nachvollziehbare Änderungen:

```text
Schritt 1:
Struktur geändert, Verhalten erhalten

Schritt 2:
Verhalten gezielt geändert, Struktur stabil gehalten
```

Typische Ergebnisse:

* kleinere Diffs
* klarere Reviews
* eindeutigere Tests
* leichteres Zurückrollen
* bessere Ursachenanalyse
* nachvollziehbare Commits

## Zusammenhang mit anderen Recipes

* `ASD-001 – Current Behavior First`
  schafft die notwendige Kenntnis und Absicherung des Ausgangsverhaltens.

* `ASD-002 – Small Safe Steps`
  liefert den Rahmen für getrennte und prüfbare Arbeitsschritte.

## Merksatz

> Erst die Struktur ändern, ohne das Verhalten zu verändern. Danach das Verhalten ändern, ohne erneut die Struktur umzubauen.
