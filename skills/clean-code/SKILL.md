---
name: clean-code
description: Richtlinien für das Schreiben von sauberem, wartbarem und gut lesbarem Code. Wende diese Regeln beim Schreiben oder Überprüfen von Code an, um Konsistenz und Qualität sicherzustellen.
---
# Clean-Code-Richtlinien

## Konstanten statt magischer Zahlen
- Ersetze fest codierte Werte durch benannte Konstanten
- Verwende aussagekräftige Konstantennamen, die den Zweck des Wertes erklären
- Platziere Konstanten am Anfang der Datei oder in einer separaten Konstantendatei

## Aussagekräftige Namen
- Variablen, Funktionen und Klassen sollten ihren Zweck erkennen lassen
- Namen sollten erklären, warum etwas existiert und wie es verwendet wird
- Vermeide Abkürzungen, außer sie sind allgemein verständlich

## Sinnvolle Kommentare
- Kommentiere nicht, was der Code tut – schreibe stattdessen selbsterklärenden Code
- Verwende Kommentare, um zu erklären, warum etwas auf eine bestimmte Weise umgesetzt wird
- Dokumentiere APIs, komplexe Algorithmen und nicht offensichtliche Seiteneffekte

## Einzelverantwortung (Single Responsibility)
- Jede Funktion sollte genau eine Aufgabe erfüllen
- Funktionen sollten klein und fokussiert sein
- Wenn eine Funktion einen Kommentar benötigt, um zu erklären, was sie tut, sollte sie aufgeteilt werden

## DRY (Don't Repeat Yourself)
- Lagere wiederholten Code in wiederverwendbare Funktionen aus
- Teile gemeinsame Logik durch geeignete Abstraktion
- Pflege eine einzige verlässliche Quelle der Wahrheit („Single Source of Truth“)

## Saubere Struktur
- Halte zusammengehörigen Code beieinander
- Organisiere Code in einer logischen Hierarchie
- Verwende konsistente Benennungsregeln für Dateien und Ordner

## Kapselung
- Verberge Implementierungsdetails
- Stelle klare Schnittstellen bereit
- Verschiebe verschachtelte Bedingungen in gut benannte Funktionen

