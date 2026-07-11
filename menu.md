# Menu

Navigationsseite für das Agentic Software Development Cookbook.

## Einstieg

* [README](README.md) – Zielbild, Grundidee und Struktur des Cookbooks
* [Milestones](milestones.md) – Projektfortschritt und wichtige Etappen
* [Open Questions](open-questions.md) – offene Fragen, Beobachtungen und Forschungsrichtungen

## Recipes

### Grundlagen

* [ASD-001 – Current Behavior First](recipes/asd-001-current-behavior-first.md)
* [ASD-002 – Small Safe Steps](recipes/asd-002-small-safe-steps.md)
* [ASD-003 – Keep Human Entry Points Small](recipes/asd-003-keep-human-entry-points-small.md)

## Recipe-Index nach Problemtyp

### Bestehenden Code sicher bearbeiten

* **ASD-001 – Current Behavior First**
  Erst das aktuelle Verhalten verstehen, dokumentieren und absichern, bevor ein Agent Änderungen vornimmt.

### Agentenarbeit begrenzen

* **ASD-002 – Small Safe Steps**
  Aufgaben in kleine, klar begrenzte und einzeln prüfbare Schritte zerlegen.

Mögliche Themen:

* klare Änderungsgrenzen
* keine unkontrollierten Refactorings
* keine Vermischung von Dokumentation, Code und Datenartefakten
* kleine, prüfbare Arbeitspakete

### Reviews und Qualitätssicherung

Noch keine Recipes.

Mögliche Themen:

* Diffs lesen
* Testläufe bewerten
* Agentenergebnisse fachlich prüfen
* Akzeptanzkriterien formulieren

### Dokumentation und Wissensaufbau

* **ASD-003 – Keep Human Entry Points Small**
  Lange Dokumentation als Projektgedächtnis erhalten und zusätzlich kurze, aktuelle Einstiegspunkte für Menschen schaffen.

Mögliche Themen:

* Chat-Ergebnisse in Projektwissen überführen
* Zwischenstände dokumentieren
* Entscheidungslog sauber halten
* Projekthistorie nutzbar machen

### Mensch-Agent-Zusammenarbeit

Noch keine Recipes.

Mögliche Themen:

* ChatGPT als Planer
* Codex oder Coding-Agent als Worker
* Mensch als Entscheider
* Übergaben zwischen Planung, Umsetzung und Review

## Geplante Recipe-Struktur

Jedes Recipe sollte möglichst kurz bleiben und ungefähr diesem Aufbau folgen:

```markdown
# ASD-000 – Titel

## Problem

Welches wiederkehrende Problem tritt auf?

## Kontext

Wann ist dieses Recipe relevant?

## Vorgehen

Welche konkrete Arbeitsweise hat sich bewährt?

## Warum das hilft

Welche Risiken werden reduziert?
Welche Qualität wird verbessert?

## Beispiel

Kurzes Beispiel aus einem echten oder abstrahierten Projekt.

## Grenzen

Wann sollte man dieses Recipe nicht oder nur vorsichtig anwenden?

## Verwandte Recipes

Links zu ähnlichen oder ergänzenden Recipes.
```

## Aktueller Stand

Belegte Recipes:

* ASD-001 – Current Behavior First
* ASD-002 – Small Safe Steps
* ASD-003 – Keep Human Entry Points Small

Noch offen:

* Abgrenzung zwischen Recipe, Pattern, Guideline und Checkliste
* Entscheidung, wie stark reale Projektbeispiele anonymisiert oder abstrahiert werden sollen
