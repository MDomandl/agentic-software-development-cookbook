# ASD-001 – Current Behavior First

## Problem

Ein Agent soll Code ändern, obwohl das aktuelle Verhalten des Systems nicht ausreichend verstanden ist.

Das führt schnell zu riskanten Änderungen:

* bestehende Fachlogik wird versehentlich verändert
* Tests prüfen nicht das relevante Verhalten
* Refactorings vermischen sich mit fachlichen Änderungen
* Fehler werden erst spät sichtbar
* Agent und Mensch diskutieren über Zielbilder, ohne den Ist-Zustand sauber zu kennen

## Grundsatz

Bevor ein Agent Verhalten verändert, muss das aktuelle Verhalten verstanden, dokumentiert und möglichst abgesichert werden.

Nicht zuerst verbessern.

Nicht zuerst umbauen.

Nicht zuerst „aufräumen“.

Zuerst klären:

> Was macht das System aktuell wirklich?

## Wann anwenden?

Dieses Recipe ist besonders wichtig, wenn:

* bestehender Code unklar oder historisch gewachsen ist
* Fachlogik im Code steckt, aber nicht dokumentiert ist
* Tests fehlen oder nur technische Details prüfen
* ein Agent Refactoring, Erweiterungen oder Bugfixes durchführen soll
* unklar ist, ob ein beobachtetes Verhalten Absicht, Bug oder Zufall ist
* mehrere Agenten oder mehrere Arbeitsschritte aufeinander aufbauen

## Vorgehen

### 1. Aktuelles Verhalten beobachten

Der Agent soll zuerst lesen, ausführen und beschreiben.

Geeignete Aufgaben:

* relevante Dateien identifizieren
* vorhandene Tests prüfen
* Beispielaufrufe suchen
* bestehende Reports, Logs oder Artefakte lesen
* CLI-Verhalten oder Programmfluss nachvollziehen
* Datenfluss und wichtige Entscheidungen beschreiben

Wichtig:

Der Agent soll noch nichts ändern.

### 2. Verhalten dokumentieren

Das beobachtete Verhalten wird kurz dokumentiert.

Zum Beispiel in:

* `docs/current_behavior.md`
* einem bestehenden Fachkonzept
* einem Abschnitt im Recipe, Ticket oder Arbeitsprotokoll
* einer Markdown-Datei nahe am betroffenen Code

Die Dokumentation soll beschreiben:

* welche Eingaben relevant sind
* welche Schritte ausgeführt werden
* welche Ausgaben entstehen
* welche Annahmen erkennbar sind
* welche offenen Fragen bleiben
* welche Risiken bei Änderungen bestehen

### 3. Verhalten absichern

Wenn möglich, wird das aktuelle Verhalten durch Tests oder Vergleichsartefakte abgesichert.

Geeignete Formen:

* Charakterisierungstests
* Snapshot-Tests
* Golden-Master-Dateien
* Beispielreports
* kleine reproduzierbare Testdaten
* CLI-Tests
* Vorher/Nachher-Vergleiche

Ziel ist nicht, das Verhalten bereits als „richtig“ zu beweisen.

Ziel ist, unbeabsichtigte Änderungen sichtbar zu machen.

### 4. Erst danach ändern

Erst wenn das aktuelle Verhalten ausreichend verstanden ist, darf der Agent Änderungen vorschlagen oder umsetzen.

Dabei sollte klar getrennt werden zwischen:

* Dokumentation des Ist-Zustands
* Absicherung des Ist-Zustands
* fachlicher Änderung
* technischem Refactoring
* neuer Funktionalität

## Geeigneter Agentenauftrag

```text
Analysiere zuerst das aktuelle Verhalten der betroffenen Funktionalität.

Ändere noch keinen produktiven Code.

Dokumentiere kurz:
- welche Dateien relevant sind
- wie der aktuelle Ablauf funktioniert
- welche Eingaben und Ausgaben wichtig sind
- welche Annahmen oder Risiken du erkennst
- welche Tests oder Artefakte das aktuelle Verhalten bereits absichern
- welche Absicherung vor einer Änderung sinnvoll wäre

Wenn du unsicher bist, markiere die Unsicherheit ausdrücklich.
```

## Geeigneter Folgeauftrag

```text
Ergänze eine minimale Absicherung für das aktuell beobachtete Verhalten.

Ziel ist nicht, das Verhalten zu verbessern, sondern unbeabsichtigte Änderungen sichtbar zu machen.

Bevorzuge kleine, nachvollziehbare Tests oder Vergleichsartefakte.
Ändere produktiven Code nur, wenn es für die Testbarkeit zwingend nötig ist.
Dokumentiere, was abgesichert wurde und was nicht.
```

## Anti-Patterns

### Direkt losprogrammieren

Der Agent beginnt sofort mit einer Lösung, ohne das bestehende Verhalten zu erklären.

Risiko:

Die Änderung sieht plausibel aus, verändert aber unbemerkt Fachlogik.

### Refactoring und Fachänderung vermischen

Der Agent räumt Code auf und ändert gleichzeitig Verhalten.

Risiko:

Später ist nicht mehr nachvollziehbar, welche Änderung welchen Effekt hatte.

### Tests nach Wunschverhalten schreiben

Tests werden direkt für das neue Zielverhalten geschrieben.

Risiko:

Das bisherige Verhalten bleibt unbekannt. Regressionen werden nicht erkannt.

### Dokumentation als Behauptung

Der Agent schreibt auf, wie das System vermutlich funktioniert, ohne Code, Tests oder Artefakte geprüft zu haben.

Risiko:

Die Dokumentation klingt sauber, ist aber nicht belastbar.

## Ergebnis

Nach Anwendung dieses Recipes gibt es mindestens eines der folgenden Ergebnisse:

* eine kurze Beschreibung des aktuellen Verhaltens
* eine Liste relevanter Dateien und Einstiegspunkte
* dokumentierte Annahmen und offene Fragen
* Tests oder Artefakte, die das aktuelle Verhalten absichern
* eine klare Grenze zwischen Ist-Zustand und geplanter Änderung

## Nutzen

Dieses Recipe macht agentische Softwareentwicklung sicherer, weil der Agent nicht auf Basis einer Vermutung arbeitet.

Es schafft einen gemeinsamen Referenzpunkt für Mensch und Agent.

Dadurch werden spätere Änderungen kleiner, überprüfbarer und besser diskutierbar.

## Merksatz

> Erst verstehen. Dann absichern. Dann ändern.
