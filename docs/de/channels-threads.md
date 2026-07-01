---
title: Channels & Threads
description: Lies Channels aus und erstelle Text-, Voice-, Kategorie- und Thread-Channels.
icon: tag
---

## Channels lesen

```lua
local channel = discord.getChannel(channelId)

if channel ~= nil then
  channel.send("Hallo aus dem Addon.")
end
```

## Channels erstellen

```lua
discord.createTextChannel(guildId, "logs", {
  topic = "Addon Logs",
  reason = "Setup"
})

discord.createVoiceChannel(guildId, "Support", {
  reason = "Setup"
})

discord.createCategory(guildId, "BotMine")
```

Methoden:

* `createTextChannel(guildId, name, options?)`
* `createVoiceChannel(guildId, name, options?)`
* `createCategory(guildId, name)`

## Threads

```lua
discord.createThread(channelId, "Diskussion", {
  autoArchiveDuration = 1440
})

discord.createThreadFromMessage(channelId, messageId, "Diskussion", {
  autoArchiveDuration = 1440
})
```

Forum-Thread:

```lua
discord.createForumThread(channelId, "Release", "Neuer Build verfügbar", {
  autoArchiveDuration = 1440
})
```

Auto-Archive-Werte:

* `60`
* `1440`
* `4320`
* `10080`
