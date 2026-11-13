---
name: adr
description: Handling von ADR (Architectural Decision Records) in Softwareprojekten. Nutze diese Richtlinien, um Entscheidungen zu dokumentieren, die Architekturentscheidungen nachvollziehbar und überprüfbar machen.
---

# ADR-Richtlinien
Ein **Architecture Decision Record (ADR)** ist ein kurzes Dokument, das eine **einzelne, architekturrelevante Entscheidung** festhält: den Kontext, die Entscheidung selbst, die betrachteten Alternativen und die Konsequenzen.

## Dateiordner und Benennung
ADR-Dokumente liegen im Projekt im Ordner `docs/adr/`. Die Dateien beginnen mit einem Zeitstempel im Format YYYYMMDD, gefolgt von einem kurzen, beschreibenden Titel. Beispiel: `20261123-architektur-entscheidungen-aufzeichnen.md`. Der beschreibende Text sollte in **Kleinbuchstaben** und mit **Bindestrichen** geschrieben werden, und 10 Worte sollten nicht überschritten werden. 

## Struktur eines ADR

Im folgenden ist die empfohlene Struktur eines ADR-Dokuments dargestellt:

```markdown
# Architektur Entscheidungen aufzeichnen

Date: 2026-11-11

## Status

Accepted

## Context

Wir müssen die in diesem Projekt getroffenen Architekturentscheidungen festhalten.

## Decision

Wir verwenden Architecture Decision Records. ADRs werden in deutscher Sprache verfasst. 

## Consequences

Unsere Entscheidungen sind nun dokumentiert und nachvollziehbar. Sie können in der Zukunft überprüft und angepasst werden.
```

Die Überschrift enthält die laufende Nummer des ADR und einen kurzen, beschreibenden Titel. 
Das Datum gibt an, wann die Entscheidung getroffen wurde. 
Der Status kann `Accepted`, `Proposed`, `Deprecated` oder `Superseded` sein.
Der Context beschreibt die Situation, die zur Entscheidung geführt hat.
Die Decision beschreibt die getroffene Entscheidung und die Alternativen, die in Betracht gezogen wurden.
Die Consequences beschreiben die Auswirkungen der Entscheidung, sowohl positive als auch negative.

## Sprache

Die ADRs sollten in deutscher Sprache verfasst werden, sofern dies nicht im ersten ADR explizit anders angegeben ist.

## Vorbereitung
- Prüfe ob der Ordner `docs/adr/` existiert.
  - Wenn der Ordner `docs/adr/` nicht existiert, erstelle ihn. 
  - Erstelle das erste ADR-Dokument entsprechend der Struktur. Frage zuvor den Benutzer in welcher Sprache die ADRs geführt werden sollen.

## Erstellen eines neuen ADRs

Die Angaben werden **Schritt für Schritt** eingeholt. Wichtig:
- Stelle **pro Nachricht genau eine Frage**. Fasse niemals mehrere Fragen in einer Nachricht zusammen.
- Warte nach jeder Frage auf die Antwort des Benutzers, bevor du die nächste Frage stellst.
- Zeige keine Vorschau auf die noch folgenden Fragen.
- Überspringe einen Schritt nur, wenn die Angabe bereits eindeutig aus dem Prompt hervorgeht.

Reihenfolge der Abfragen:
1. **Titel:** Frage nach dem Titel des ADRs.
2. **Status:** Frage nach dem Status (`Accepted` oder `Proposed`). Nutze dafür das Tool `AskUserQuestion` mit den beiden Optionen.
3. **Kontext:** Frage, worum es in dem ADR geht und was zur Entscheidung geführt hat (Context).
4. **Entscheidung:** Frage, welche Entscheidung getroffen wurde (Decision).
5. **Alternativen:** Frage, ob eine andere denkbare Lösung verworfen wurde und warum.
6. **Konsequenzen:** Frage nach den positiven und negativen Konsequenzen der Entscheidung (Consequences).

Danach:
- Lege die Datei mit dem aktuellen Zeitstempel im Ordner `docs/adr/` an.
- Formuliere die gesammelten Angaben aus und trage sie entsprechend der Struktur ein. Verworfene Alternativen gehören in den Abschnitt Decision.