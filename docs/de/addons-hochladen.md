---
title: Addons hochladen
description: Bereite ein BotMine Addon vor, lade einen ZIP-Build hoch und reiche es zur Prüfung ein.
icon: upload
---

## Überblick

Diese Anleitung beschreibt, wie du ein eigenes BotMine Addon vorbereitest, im Dashboard hochlädst und zur Prüfung einreichst. Ein Addon wird beim ersten Speichern privat als Draft angelegt. Öffentlich sichtbar wird es erst nach erfolgreichem Review durch Staff.

## Voraussetzungen

Du brauchst:

* einen BotMine Account
* einen klaren Addon-Namen
* eine kurze Beschreibung für Listen und Cards
* eine längere Beschreibung für die Detailseite
* eine passende Kategorie
* eine Version, zum Beispiel `1.0.0`
* ein ZIP-Build, wenn das Addon installierbar sein soll
* optional ein Thumbnail als `png`, `jpg`, `jpeg`, `webp` oder `gif`

## Addon erstellen

Öffne im Dashboard:

```text
Dashboard > Addons > Neues Addon
```

Direkter Pfad:

```text
/dashboard/addons/new
```

Fülle anschließend die Addon-Daten aus:

* `Name`: sichtbarer Name des Addons
* `Kurzbeschreibung`: ein kurzer Satz, der im Marketplace gut scanbar ist
* `Beschreibung`: Zweck, Zielgruppe und enthaltene Features
* `Kategorie`: passende Addon-Kategorie
* `Version`: aktuelle Version des Addons
* `Thumbnail`: optionales Bild für Marketplace und Detailseite
* `Config Schema`: optionale Konfigurationsfelder für Bot-Installationen
* `Permissions`: Runtime-Rechte, die dein Addon braucht
* `Addon-ZIP`: optionaler erster Build

Beim Speichern wird das Addon privat als Draft angelegt. Es ist noch nicht öffentlich sichtbar.

## ZIP-Build vorbereiten

Das Addon wird als ZIP hochgeladen. Die ZIP muss sicher und eindeutig strukturiert sein.

Erlaubt:

* ZIP-Datei bis 50 MB
* maximal 1000 Dateien im ZIP
* entpackte Gesamtgröße bis 100 MB
* einzelne Dateien bis 25 MB
* Manifest-Datei `addon.yml` oder `addon.yaml`

Nicht erlaubt:

* Pfade mit `../`
* absolute Pfade
* Symlinks
* ZIP64-Builds
* fehlende oder nicht lesbare Manifest-Datei

## Manifest

Jeder Build braucht eine `addon.yml` oder `addon.yaml`.

Pflichtfelder:

```yaml
id: dein-addon-id
name: Mein Addon
version: 1.0.0
entry: index.lua
```

Hinweise:

* `id` wird beim Upload intern auf die BotMine-Addon-UUID angepasst.
* `entry` muss auf eine Datei zeigen, die im ZIP existiert.
* In diesen Lua-Docs wird `index.lua` als Beispiel verwendet. Entscheidend ist der tatsächliche Dateiname in deinem ZIP.
* Die Manifest-Datei darf im Root des ZIP liegen oder in einem einzelnen Projektordner innerhalb des ZIP.

Beispiel mit Manifest im Root:

```text
my-addon.zip
├── addon.yml
├── index.lua
└── package.json
```

Beispiel mit einem Projektordner:

```text
my-addon.zip
└── my-addon/
    ├── addon.yml
    ├── index.lua
    └── package.json
```

## Weitere Builds hochladen

Nach dem Erstellen findest du die Build-Verwaltung auf der Addon-Detailseite.

Typischer Pfad:

```text
/dashboard/addons/{addonId}/builds
```

Dort kannst du neue ZIP-Builds hochladen. Jeder Build wird privat gespeichert und ist nur für berechtigte Nutzer, Creator oder Staff abrufbar.

## Zur Prüfung einreichen

Wenn dein Addon fertig ist:

1. Öffne die Addon-Detailseite.
2. Prüfe Name, Beschreibung, Kategorie, Version, Config und Permissions.
3. Lade mindestens den Build hoch, der geprüft werden soll.
4. Klicke auf `Zur Prüfung einreichen`.

Das Addon bekommt dann den Status:

```text
IN_REVIEW
```

Während des Reviews ist es weiterhin nicht öffentlich sichtbar.

## Review durch Staff

Staff prüft:

* Beschreibung und Darstellung
* Kategorie und Marketplace-Tauglichkeit
* ZIP-Build und Manifest
* Runtime-Permissions
* Sicherheit und offensichtliche Missbrauchsrisiken
* ob das Addon installierbar und nachvollziehbar ist

Mögliche Ergebnisse:

* `PUBLISHED`: Addon wurde freigegeben und kann sichtbar werden.
* `DRAFT` oder `HIDDEN`: Addon muss überarbeitet werden.
* `DISABLED` oder `ARCHIVED`: Addon ist nicht nutzbar oder wurde entfernt.

## Updates nach Veröffentlichung

Wenn du ein bereits veröffentlichtes Addon bearbeitest, wird es wieder aus der Sichtbarkeit genommen und erneut in den Review-Prozess verschoben.

Das ist wichtig, weil sich durch Updates Code, Permissions, Beschreibung oder Verhalten ändern können.

## Gute Beschreibung schreiben

Eine gute Addon-Beschreibung beantwortet:

* Was macht das Addon?
* Welches Problem löst es?
* Für welche Discord-Server ist es gedacht?
* Welche Konfiguration ist nötig?
* Welche Rechte braucht es?
* Gibt es bekannte Limits?

Vermeide:

* unklare Marketingtexte ohne konkrete Funktionen
* falsche Versprechen
* externe Downloads außerhalb von BotMine
* verschleierte oder nicht erklärte Berechtigungen

## Checkliste vor dem Einreichen

* Addon hat einen klaren Namen.
* Kurzbeschreibung ist verständlich.
* Beschreibung erklärt Features und Nutzung.
* Kategorie passt.
* Version ist gesetzt.
* ZIP enthält `addon.yml` oder `addon.yaml`.
* Manifest enthält `id`, `name`, `version`, `entry`.
* `entry`-Datei existiert im ZIP.
* Keine unsicheren Pfade oder Symlinks im ZIP.
* Permissions sind vollständig und nachvollziehbar.
* Config Schema ist gültig oder leer.
* Der Build ist der Build, der reviewed werden soll.

## Fehler beim Upload

Häufige Ursachen:

* ZIP fehlt.
* Datei ist keine ZIP.
* ZIP ist zu groß.
* `addon.yml` fehlt.
* Manifest-Felder fehlen.
* `entry` zeigt auf eine nicht vorhandene Datei.
* ZIP enthält unsichere Pfade.
* ZIP enthält Symlinks.

Wenn ein Upload fehlschlägt, korrigiere den Build lokal und lade eine neue ZIP hoch.

## Sichtbarkeit

Privat gespeicherte Addons sind nur für dich und berechtigte Staff-Bereiche sichtbar.

Ein Addon wird erst öffentlich, wenn Staff es freigegeben hat und es als sichtbar markiert ist. Eigene Addons kannst du für deine Bots auch ohne gekauftes Entitlement hinzufügen, sofern die Plattform das Addon für dich als Creator erkennt.
