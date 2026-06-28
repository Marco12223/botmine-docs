---
title: Lua Addon SDK
description: Lerne, wie du sichere Lua Addons für BotMine baust.
icon: rocket_launch
---

## Überblick

BotMine Addons laufen in einer kontrollierten Lua Runtime.

Du bekommst Zugriff auf eine sichere Discord API, ohne direkt JDA, den Bot Token oder interne Core-Daten zu berühren.

## Beispiel

```lua
discord.onReady(function(event)
    logger.info("Addon loaded on " .. event.botName)
end)
```

## Regeln

- Nutze nur die freigegebenen APIs.
- Prüfe Permissions vor Moderationsaktionen.
- Blockiere niemals den Lua Runtime Thread.