# Agentic Software Development Cookbook

Ein praxisbasiertes Cookbook für agentische Softwareentwicklung.

Dieses Repository sammelt wiederverwendbare Vorgehensweisen, Muster und Entscheidungsregeln für die Arbeit mit KI-Agenten in Softwareprojekten.

Der Fokus liegt nicht auf Theorie, Tool-Vergleichen oder abstrakten Zukunftsvisionen, sondern auf konkreten Problemen aus echten Projekten:

* Wie starte ich mit einem bestehenden Codebestand?
* Wie verhindere ich, dass ein Agent unkontrolliert umbaut?
* Wie dokumentiere ich Zwischenergebnisse so, dass sie später wiederverwendbar sind?
* Wie teile ich Arbeit sinnvoll zwischen Mensch, ChatGPT und Coding-Agent auf?
* Wie mache ich Agentenarbeit nachvollziehbar, testbar und sicher?

## Grundidee

Agentische Softwareentwicklung funktioniert am besten, wenn der Mensch nicht einfach nur Aufgaben delegiert, sondern den Rahmen vorgibt:

* Ziel klären
* aktuellen Zustand verstehen
* kleine Arbeitspakete schneiden
* Sicherheitsgrenzen setzen
* Änderungen prüfen
* Wissen dokumentieren
* Erfahrungen in wiederverwendbare Muster überführen

Dieses Cookbook sammelt solche Muster als kurze Recipes.

## Zielgruppe

Dieses Cookbook richtet sich an Entwicklerinnen und Entwickler, Tech Leads und experimentierfreudige Praktiker, die KI-Agenten nicht nur zum Code-Schreiben, sondern als Teil eines nachvollziehbaren Entwicklungsprozesses einsetzen wollen.

Es ist besonders hilfreich für Menschen, die bereits eigene Projekte mit ChatGPT, Codex, IDE-Agenten oder ähnlichen Werkzeugen bearbeiten und ihre Arbeitsweise strukturierter, sicherer und wiederholbarer machen möchten.

## Was dieses Cookbook ist

Dieses Cookbook ist:

* praxisorientiert
* problemorientiert
* kurz und referenzierbar
* aus echten Projekten abgeleitet
* bewusst iterativ

Jedes Recipe beschreibt ein wiederkehrendes Problem, eine bewährte Vorgehensweise und möglichst konkrete Hinweise zur Anwendung.

## Was dieses Cookbook nicht ist

Dieses Cookbook ist kein vollständiges Lehrbuch über KI, kein Framework und keine allgemeingültige Methodik.

Es ersetzt keine Architekturentscheidungen, kein Code Review, keine Tests und keine fachliche Verantwortung.

KI-Agenten können helfen, schneller und strukturierter zu arbeiten. Die Verantwortung für Ziel, Qualität, Sicherheit und Freigabe bleibt beim Menschen.

## Struktur

* `README.md` – Einstieg, Zielbild und Grundsätze
* `menu.md` – Navigationsseite durch das Cookbook
* `recipes/` – einzelne wiederverwendbare Recipes
* `open-questions.md` – offene Fragen, Beobachtungen und Forschungsrichtungen
* `milestones.md` – Projektfortschritt und wichtige Etappen

## Erstes Recipe

Das erste belegte Recipe ist:

**ASD-001 – Current Behavior First**

Kernaussage:

> Bevor ein Agent Verhalten verändert, muss das aktuelle Verhalten verstanden, dokumentiert und möglichst durch Tests oder reproduzierbare Beobachtungen abgesichert werden.

Dieses Muster entstand aus praktischer Projektarbeit und bildet einen grundlegenden Sicherheitsanker für agentische Softwareentwicklung.

## Arbeitsweise

Dieses Cookbook entsteht iterativ.

Neue Recipes werden nicht erfunden, um eine schöne Struktur zu füllen. Sie entstehen aus konkreten Situationen, Problemen und Lernerfahrungen in echten Projekten.

Typischer Ablauf:

1. Ein wiederkehrendes Problem wird in der Praxis sichtbar.
2. Die Lösung oder Arbeitsweise wird ausprobiert.
3. Die Erfahrung wird verdichtet.
4. Daraus entsteht ein kurzes Recipe.
5. Das Recipe wird später durch weitere Projekte geschärft.

## Beispielhafte Erprobungsprojekte

Die Patterns werden unter anderem anhand praktischer Projekte entwickelt und überprüft, zum Beispiel:

* `aktien_oop` – Backtesting, Paper-Runner, Reports, Sicherheitsgrenzen, Agentenarbeit an bestehendem Code
* `achtsam_morden` – Theater-/Text-/Projektarbeit als nicht-klassisches Softwareprojekt mit agentischer Unterstützung

Diese Projekte dienen nicht als fertige Blaupause, sondern als Erfahrungsbasis.

## Leitprinzipien

* Erst verstehen, dann verändern.
* Kleine Schritte sind sicherer als große Umbauten.
* Der Mensch definiert Ziel, Grenzen und Freigabe.
* Agentenarbeit muss nachvollziehbar bleiben.
* Dokumentation ist Teil des Ergebnisses.
* Tests, Diffs und Reviews sind Sicherheitswerkzeuge.
* Gute Prompts ersetzen keine gute Projektstruktur.
* Jedes Recipe muss in der Praxis nützlich sein.

## Status

Früher Aufbau.

Das Cookbook befindet sich in einer frühen, experimentellen Phase. Inhalte dürfen unvollständig, vorläufig oder noch unausgereift sein.

Wichtiger als Vollständigkeit ist, dass jedes Recipe aus realer Arbeit entsteht und später wiederverwendbar ist.
