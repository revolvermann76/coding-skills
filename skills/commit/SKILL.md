---
name: commit
description: Dieser Skill dient dem standardisierten Committen in ein Git Repository.
globs: 
---

# Commit

## Commit-Kommentar

Der Commit-Kommentar folgt dem Standard Conventional Commits und hat folgendes Format:

```
<type>(<scope>): <Ticket-Nummer> - <summary>

<description>
```

Sprache: grundsätzlich Deutsch. Englische Fachbegriffe werden nur verwendet, wenn es kein passendes deutsches Äquivalent gibt.

Der Type wird aus dem Namen des Branches abgeleitet:

| Typ | Verwendung |
|---|---|
| feat | Neue Funktionalität |
| fix | Fehlerbehebung |
| hotfix | Kritische Fehlerbehebung, die auch in einen Release-Branch gemerged werden muss |
| refactor | Umstrukturierung ohne fachliche Änderung |
| test | Tests hinzufügen oder anpassen |
| docs | Änderungen an der Dokumentation |
| chore | Wartungsarbeiten (Dependencies, Build, etc.) |
| style | Formatierung, fehlende Semikolons o.Ä. (kein fachlicher Code) |
| perf | Performance-Verbesserungen |
| ci | Änderungen an CI/CD-Konfiguration |
| revert | Rückgängigmachen eines früheren Commits |

Der Scope ist optional und beschreibt den betroffenen Bereich (z.B. Modul- oder Komponentenname).

Die Summary steht im Imperativ (`add`, `fix`, `update` statt `added`, `fixed`, `updated`) und ist eine kurze Zusammenfassung in maximal zehn Worten und beschreibt, was der Commit für Änderungen gegenüber dem letzten Commit enthält.

Description ist eine detailliertere Auflistung aller Änderungen, z.B. als Stichpunkte.

Die Ticket-Nummer wird angegeben, damit die Jira-Integration den Commit automatisch zuordnen kann. Sie lässt sich aus dem Branch-Namen ableiten. Sollte sich dort keine Ticket-Nummer ableiten lassen, entfällt die Angabe.

Beispiel
```
feat(auth): VOIS-123 - OAuth2-Login ergänzen

- OAuth2-Flow mit dem Identity Provider integriert
- Token-Refresh-Handling hinzugefügt

```

## Ablauf des Skills

- Erstelle den Commit-Kommentar und zeige ihn an
- Stelle eine Rückfrage an den Benutzer, ob dieser damit einverstanden ist, oder ob er Änderungen vornehmen möchte
- stage alle geänderten Dateien, es sei denn, der Benutzer hat in seiner Anfrage explizip andere oder einschränkende Anweisungen gegeben
- committe die Änderungen
- stelle eine Rückfrage an den Benutzer, ob dieser die Daten auch ins Git pushen möchte
- falls der Benutzer ins Git pushen möchte, dann führe das aus; der SSH-Key wird von `pageant` zur Verfügung gestellt
- in der Serverantwort beim Push ist in der Regel ein Link enthalten. Zeige diesen Link an