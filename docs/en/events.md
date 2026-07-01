---
title: Events
description: React to ready, message, guild, and component events.
icon: bolt
---

## Ready

```lua
discord.onReady(function(event)
  logger.info("Bot ready: " .. event.botName)
  logger.info("Guilds: " .. event.guildCount)
end)
```

`ReadyEvent` contains:

* `botId`
* `botName`
* `guildCount`

## Messages

```lua
discord.onMessage(function(event)
  if event.authorIsBot then
    return
  end

  if event.matches("!", "help") then
    event.reply("Available commands: `/ping`")
  end
end)
```

`MessageEvent` includes:

* `content`
* `authorId`
* `authorName`
* `channelId`
* `messageId`
* `guildId`
* `member`
* `reply(content)`
* `send(content)`
* `delete()`
* `addReaction(emoji)`
* `hasPermission(permission)`

## Guild events

```lua
discord.onGuildJoin(function(event)
  logger.info("New guild: " .. event.guildName)
end)

discord.onGuildLeave(function(event)
  logger.info("Left guild: " .. event.guildName)
end)
```

## Component events

Component events are registered by `customId`:

```lua
discord.onButton("confirm", function(event)
  event.replyEphemeral("Confirmed.")
end)

discord.onSelectMenu("role_select", function(event)
  event.replyEphemeral("Selected: " .. event.values[1])
end)

discord.onModalSubmit("feedback", function(event)
  event.replyEphemeral("Thanks for your feedback.")
end)
```
