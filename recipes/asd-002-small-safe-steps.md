# ASD-002 – Small Safe Steps

## Problem

Ein Agent bekommt eine zu große Aufgabe und versucht, viele Änderungen in einem Schritt umzusetzen.

Das führt schnell zu Problemen:

* zu viele Dateien werden gleichzeitig geändert
* fachliche Änderung, Refactoring und Tests vermischen sich
* Reviews werden schwer
* Fehlerquellen sind nicht mehr klar zuzuordnen
* Zwischenergebnisse sind nicht sinnvoll prüfbar
* der Agent verliert den Bezug zum ursprünglichen Ziel

## Grundsatz

Agentische Softwareentwicklung wird sicherer, wenn Änderungen in kleine, prüfbare Schritte zerlegt werden.

Nicht:

> „Baue das ganze Modul um.“

Sondern:

> „Führe den nächsten kleinsten sinnvollen Schritt aus und mache ihn überprüfbar.“

## Wann anwenden?

Dieses Recipe ist besonders wichtig, wenn:

* mehrere Dateien betroffen sind
* bestehendes Verhalten erhalten bleiben soll
* Refactoring geplant ist
* neue Funktionalität ergänzt wird
* Tests nachgezogen werden müssen
* Unsicherheit über Fachlogik oder Seiteneffekte besteht
* mehrere Agentenläufe aufeinander aufbauen

## Vorgehen

### 1. Ziel in kleine Schritte zerlegen

Der Agent soll zuerst eine kurze Schrittfolge vorschlagen.

Jeder Schritt sollte:

* ein klares Ziel haben
* möglichst wenig Dateien betreffen
* einzeln prüfbar sein
* bei Bedarf einzeln revertierbar sein
* keine unnötigen Nebenänderungen enthalten

Beispiele für gute Schritte:

* erst Dokumentation ergänzen
* erst bestehenden Test lesen oder reparieren
* erst Charakterisierungstest schreiben
* erst eine kleine Funktion extrahieren
* erst eine CLI-Option ergänzen
* erst einen Report um ein Feld erweitern

### 2. Nur den nächsten Schritt ausführen

Der Agent soll nicht automatisch den gesamten Plan abarbeiten.

Nach jedem Schritt wird geprüft:

* Was wurde geändert?
* Warum wurde es geändert?
* Wie wurde es geprüft?
* Hat sich unerwartet etwas verändert?
* Ist der nächste Schritt noch sinnvoll?

### 3. Änderungen sichtbar begrenzen

Ein guter Agentenauftrag enthält klare Grenzen.

Zum Beispiel:

* „Ändere nur Dokumentation.“
* „Ändere keinen produktiven Code.“
* „Ändere nur Tests.“
* „Ändere nur diese Datei.“
* „Führe keine Batch-Runs aus.“
* „Erzeuge keine neuen Reports.“
* „Keine fachliche Änderung in diesem Schritt.“

Grenzen sind kein Misstrauen gegenüber dem Agenten.

Sie machen Arbeit überprüfbar.

### 4. Nach jedem Schritt prüfen

Jeder kleine Schritt braucht eine passende Prüfung.

Mögliche Prüfungen:

* `git diff`
* relevante Tests
* Linter oder Formatierung
* Beispielaufruf
* Report-Vergleich
* manuelle Review
* Abgleich mit Dokumentation

Wichtig:

Die Prüfung muss zum Schritt passen.
Nicht jeder Schritt braucht die komplette Testsuite.

## Geeigneter Agentenauftrag

```text id="lp08rv"
Zerlege die Aufgabe zuerst in kleine, überprüfbare Schritte.

Führe danach nur den ersten sinnvollen Schritt aus.

Begrenze die Änderung bewusst:
- keine unnötigen Dateien ändern
- keine fachliche Änderung mit Refactoring vermischen
- keine nicht angeforderten Reports oder Daten erzeugen
- keine Folgeaufgaben automatisch mit erledigen

Dokumentiere am Ende:
- was geändert wurde
- warum es geändert wurde
- wie du es geprüft hast
- welcher nächste kleine Schritt sinnvoll wäre
```

## Geeigneter Folgeauftrag

```text id="mv09kl"
Prüfe den aktuellen Arbeitsstand.

Bitte beschreibe:
- welche Dateien geändert wurden
- ob die Änderungen zur Aufgabe passen
- ob fachliche Änderung, Refactoring und Tests sauber getrennt sind
- welche Prüfung bereits erfolgt ist
- ob der nächste Schritt sicher begonnen werden kann

Nimm keine weiteren Änderungen vor.
```

## Anti-Patterns

### Der große Wurf

Der Agent setzt die komplette Zielarchitektur in einem Durchlauf um.

Risiko:

Die Änderung ist schwer prüfbar und kaum sauber zu reviewen.

### Nebenbei-Aufräumen

Der Agent korrigiert Formatierung, benennt Variablen um oder räumt angrenzenden Code auf, obwohl das nicht Teil der Aufgabe war.

Risiko:

Das eigentliche Diff wird unnötig groß.

### Tests, Refactoring und Feature in einem Schritt

Der Agent schreibt Tests, refactort Code und ändert Verhalten gleichzeitig.

Risiko:

Bei Fehlern ist unklar, welche Änderung die Ursache war.

### Automatischer Durchmarsch

Der Agent arbeitet nach einem Plan mehrere Schritte ab, ohne Zwischenergebnis und Review.

Risiko:

Ein früher Fehler wird in spätere Schritte weitergetragen.

## Ergebnis

Nach Anwendung dieses Recipes entsteht ein kleiner, überprüfbarer Arbeitsschritt.

Typische Ergebnisse:

* ein kleines Diff
* eine klar begrenzte Dokumentationsänderung
* ein einzelner Test
* eine kleine technische Vorbereitung
* ein nachvollziehbarer Zwischenstand
* ein klar benannter nächster Schritt

## Nutzen

Kleine Schritte machen Agentenarbeit kontrollierbarer.

Sie erleichtern Review, Tests und Fehlersuche.

Außerdem entsteht ein sauberer Arbeitsrhythmus:

> planen, begrenzen, ändern, prüfen, zusammenfassen.

## Merksatz

> Lieber fünf sichere kleine Schritte als ein großer unprüfbarer Sprung.
