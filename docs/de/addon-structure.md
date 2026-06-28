---
title: Addon-Struktur
description: Verstehe, wie ein BotMine Addon aufgebaut ist und welche Dateien benötigt werden.
icon: folder
---

## Überblick

Ein BotMine Addon ist ein kleines Lua-Paket, das vom BotCore geladen wird.

Jedes Addon besteht mindestens aus einer Manifest-Datei und einer Lua-Einstiegsdatei. Optional kann eine Type-Datei für Autocomplete und bessere Developer Experience ergänzt werden.

## Dateistruktur

```txt
my-addon/
├─ plugin.yml
├─ main.lua
└─ types/
   └─ botmine.lua
```

## `plugin.yml`

Die `plugin.yml` beschreibt dein Addon. Dort stehen Name, Version, Einstiegspunkt, Autor, Beschreibung und benötigte Berechtigungen.

```yaml
name: WelcomeTools
version: 1.0.0
main: main.lua
author: Marco
description: Adds welcome messages, moderation commands and panels.

permissions:
  - SEND_MESSAGES
  - EMBED_LINKS
  - MANAGE_MESSAGES
```

## `main.lua`

Die `main.lua` ist der Einstiegspunkt deines Addons. Diese Datei wird vom BotCore geladen und ausgeführt.

```lua
discord.onReady(function(event)
    logger.info("Addon loaded on " .. event.botName)
end)

discord.onMessage(function(event)
    if event.authorIsBot then
        return
    end

    if event.matches("!", "ping") then
        event.reply("Pong from BotMine!")
    end
end)
```

## `types/botmine.lua`

Die Datei `types/botmine.lua` ist optional.

Sie kann LuaLS-Typdefinitionen enthalten, damit Entwickler Autocomplete, Parameter-Hints und bessere Fehlermeldungen im Editor bekommen.

Diese Datei wird nicht für die Runtime benötigt. Sie ist nur für die Entwicklung gedacht.

## Regeln

- `main.lua` enthält die eigentliche Addon-Logik.
- `plugin.yml` beschreibt Metadaten und angeforderte Permissions.
- `types/botmine.lua` kann die LuaLS-Meta-Library für Autocomplete enthalten.
- Addons dürfen nur die freigegebenen BotMine APIs verwenden.
- Addons bekommen keinen direkten Zugriff auf JDA, Environment-Variablen oder den Bot Token.