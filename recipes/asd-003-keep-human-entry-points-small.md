# ASD-003 – Keep Human Entry Points Small

## Problem

Agenten können sehr große Dokumentationen erzeugen, fortschreiben und auswerten.

Für Menschen werden solche Dokumente aber schnell zu groß.

Eine lange Projektdokumentation kann fachlich wertvoll sein, aber trotzdem im Alltag kaum noch gelesen werden.

Dann entsteht ein Risiko:

> Es ist dokumentiert, aber niemand findet schnell heraus, was gerade wichtig ist.

## Grundsatz

Lange Dokumentation darf als Projektgedächtnis existieren.

Für die tägliche Arbeit braucht es zusätzlich kleine, aktuelle Einstiegspunkte für Menschen.

Nicht jedes Detail muss kurz sein.

Aber der Einstieg muss kurz sein.

## Wann anwenden?

Dieses Recipe ist besonders wichtig, wenn:

* eine Projektdokumentation stark wächst
* Agenten viele Zwischenschritte dokumentieren
* chronologische Arbeitsprotokolle entstehen
* Menschen den aktuellen Stand schnell verstehen müssen
* neue Agentenläufe einen klaren Startpunkt brauchen
* Entscheidungen, Sicherheitsgrenzen oder nächste Schritte schwer auffindbar werden

## Vorgehen

### 1. Langdokumentation als Gedächtnis behandeln

Lange Dokumentation ist nicht automatisch schlecht.

Sie kann wertvoll sein als:

* Arbeitsprotokoll
* Audit Trail
* Entscheidungsverlauf
* Nachschlagewerk
* Kontext für Agenten
* Beleg für frühere Annahmen und Grenzen

Aber sie sollte nicht der einzige Einstiegspunkt bleiben.

### 2. Kleine Einstiegsschicht ergänzen

Zusätzlich zur Langdokumentation sollte es eine kurze Datei geben, die den aktuellen Stand zusammenfasst.

Geeignete Namen:

* `docs/current_project_state.md`
* `docs/project_overview.md`
* `docs/current_state.md`
* `docs/README.md`

Diese Datei sollte bewusst kurz bleiben.

Sie beantwortet vor allem:

* Was ist das Ziel?
* Was funktioniert aktuell?
* Was sind die wichtigsten Entscheidungen?
* Welche Sicherheitsgrenzen gelten?
* Was ist der nächste sinnvolle Schritt?
* Wo stehen die Details?

### 3. Navigation statt Wiederholung

Die kurze Einstiegsschicht soll die Langdokumentation nicht ersetzen.

Sie soll auf wichtige Details verweisen.

Gute Kurz-Doku wiederholt nicht alles, sondern führt gezielt hin:

```text id="p3v4m7"
Details zum historischen Paper-Replay siehe:
docs/strategy_analysis.md, Abschnitt 08.60–08.95
```

So bleibt die Langdokumentation erhalten, aber Menschen müssen sie nicht vollständig lesen, um arbeitsfähig zu sein.

### 4. Regelmäßig verdichten

Wenn Agenten viele neue Details dokumentieren, sollte gelegentlich eine Verdichtung erfolgen.

Dabei wird geprüft:

* Was ist noch aktuell?
* Welche Entscheidungen sind weiterhin gültig?
* Welche offenen Fragen wurden beantwortet?
* Welche Risiken sind neu?
* Welche Details gehören nur ins Archiv?
* Was muss in den menschlichen Einstiegspunkt?

Wichtig:

Verdichten heißt nicht löschen.

Verdichten heißt: das Wichtige wieder sichtbar machen.

## Geeigneter Agentenauftrag

```text id="d8k1vz"
Lies die vorhandene Projektdokumentation und erstelle daraus einen kurzen menschlichen Einstiegspunkt.

Ziel ist keine vollständige Zusammenfassung.

Erstelle eine kurze, aktuelle Datei mit:
- Projektziel
- aktuellem Stand
- wichtigsten Entscheidungen
- geltenden Sicherheitsgrenzen
- offenen Fragen
- nächsten sinnvollen Schritten
- Verweisen auf die relevanten Detailstellen

Ändere die Langdokumentation nicht.
Erfinde keine fehlenden Informationen.
Markiere Unsicherheiten ausdrücklich.
```

## Geeigneter Folgeauftrag

```text id="x6r9qp"
Prüfe, ob der menschliche Einstiegspunkt noch aktuell ist.

Vergleiche ihn mit den zuletzt ergänzten Abschnitten der Langdokumentation.

Aktualisiere nur die kurze Einstiegsschicht.
Erhalte sie bewusst knapp.
Verschiebe Details nicht unnötig aus der Langdokumentation in die Einstiegsschicht.
```

## Anti-Patterns

### Eine riesige Datei als einziger Einstieg

Alle Informationen stehen in einer sehr langen Datei.

Risiko:

Formal ist alles dokumentiert, praktisch liest es kaum jemand.

### Vollständige Zusammenfassung

Der Agent versucht, eine lange Dokumentation vollständig in eine zweite lange Dokumentation umzuschreiben.

Risiko:

Es entsteht nur eine weitere schwer lesbare Datei.

### Details statt Entscheidungen

Die Einstiegsschicht enthält zu viele technische Einzelheiten.

Risiko:

Der eigentliche aktuelle Stand geht wieder unter.

### Veralteter Überblick

Die kurze Übersicht wird einmal erstellt, aber nie aktualisiert.

Risiko:

Menschen vertrauen einer kompakten Datei, die nicht mehr stimmt.

## Ergebnis

Nach Anwendung dieses Recipes gibt es zwei unterschiedliche Dokumentationsschichten:

```text id="kn8c2s"
Langdokumentation:
vollständig, chronologisch, detailreich, agentenfreundlich

Kurzer Einstiegspunkt:
aktuell, knapp, entscheidungsorientiert, menschenfreundlich
```

Typische Ergebnisse:

* eine kurze `current_project_state.md`
* ein aktualisierter Projektüberblick
* klare Links in die Langdokumentation
* sichtbare nächste Schritte
* weniger Einstiegshürde für Reviews und neue Agentenläufe

## Nutzen

Dieses Recipe verhindert, dass Dokumentation nur noch Archiv ist.

Es bewahrt die Vorteile langer Agenten-Dokumentation, ohne Menschen damit zu überfordern.

So bleibt das Projekt für Menschen steuerbar und für Agenten nachvollziehbar.

## Merksatz

> Lange Doku ist gut fürs Gedächtnis. Kurze Doku ist gut fürs Arbeiten.
