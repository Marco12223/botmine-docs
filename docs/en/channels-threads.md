---
title: Channels & Threads
description: Read channels and create text, voice, category, and thread channels.
icon: tag
---

## Read channels

```lua
local channel = discord.getChannel(channelId)

if channel ~= nil then
  channel.send("Hello from the addon.")
end
```

## Create channels

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

Methods:

* `createTextChannel(guildId, name, options?)`
* `createVoiceChannel(guildId, name, options?)`
* `createCategory(guildId, name)`

## Threads

```lua
discord.createThread(channelId, "Discussion", {
  autoArchiveDuration = 1440
})

discord.createThreadFromMessage(channelId, messageId, "Discussion", {
  autoArchiveDuration = 1440
})
```

Forum thread:

```lua
discord.createForumThread(channelId, "Release", "New build available", {
  autoArchiveDuration = 1440
})
```

Auto archive values:

* `60`
* `1440`
* `4320`
* `10080`
