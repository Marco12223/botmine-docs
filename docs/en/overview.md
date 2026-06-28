---
title: Lua Addon SDK
description: Learn how to build safe Lua addons for BotMine.
icon: rocket_launch
---

## Overview

BotMine addons run inside a controlled Lua runtime.

You get access to a safe Discord API without touching JDA, the bot token or internal core data.

## Example

```lua
discord.onReady(function(event)
    logger.info("Addon loaded on " .. event.botName)
end)
```

## Rules

- Use only the exposed APIs.
- Check permissions before moderation actions.
- Never block the Lua runtime thread.