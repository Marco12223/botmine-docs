---
title: BotMine Addon Entwicklung
description: Entwickle, paketisiere und veröffentliche sichere BotMine Addons.
icon: rocket_launch
---

## Überblick

BotMine Addons erweitern Bots um eigene Funktionen, ohne dass du direkt mit der Discord API oder sensibler Infrastruktur arbeiten musst. Addons laufen in einer kontrollierten Lua-Umgebung und verwenden das BotMine Lua SDK als sichere Schnittstelle zu Nachrichten, Slash Commands, Interaktionen, Konfiguration, Storage, HTTP und Logging.

Diese Dokumentation richtet sich an Creator, die eigene Addons bauen, testen und im BotMine Marketplace veröffentlichen möchten.

## Was du mit Addons bauen kannst

Ein Addon kann zum Beispiel:

* auf Nachrichten und Events reagieren
* Slash Commands registrieren
* Embeds, Buttons, Select Menus und Modals verwenden
* Rollen vergeben oder Moderationsaktionen ausführen
* persistente Daten im Addon-Storage speichern
* externe APIs über den sicheren HTTP-Wrapper ansprechen
* konfigurierbare Felder für Bot-Installationen bereitstellen

Welche Aktionen ein Addon ausführen darf, hängt von den angeforderten Permissions und der Plattformprüfung ab.

## Typischer Ablauf

1. Addon lokal entwickeln.
2. Manifest `addon.yml` oder `addon.yaml` anlegen.
3. Addon-Dateien als ZIP packen.
4. Addon im Dashboard erstellen.
5. ZIP-Build hochladen.
6. Addon zur Prüfung einreichen.
7. Nach Freigabe im Marketplace veröffentlichen lassen.

## Wichtige Dateien

Jeder veröffentlichbare Build braucht ein Manifest. Das Manifest beschreibt mindestens ID, Name, Version und Einstiegspunkt.

```yaml
id: mein-addon
name: Mein Addon
version: 1.0.0
entry: index.lua
```

Der Wert von `entry` muss auf eine Datei zeigen, die im ZIP enthalten ist. Beim Upload wird die `id` intern auf die BotMine-Addon-UUID angepasst.

## Nächste Schritte

Lies zuerst die Anleitung zum Hochladen und Einreichen von Addons. Danach kannst du in den SDK-Seiten gezielt nachschlagen, wie du Nachrichten sendest, Events verarbeitest, Storage nutzt oder HTTP-Anfragen ausführst.
