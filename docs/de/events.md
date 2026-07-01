---
title: Events
description: Reagiere auf Ready-, Message-, Guild- und Komponenten-Events.
icon: bolt
---

## Ready

```lua
discord.onReady(function(event)
  logger.info("Bot bereit: " .. event.botName)
  logger.info("Guilds: " .. event.guildCount)
end)
```

`ReadyEvent` enthält:

* `botId`
* `botName`
* `guildCount`

## Nachrichten

```lua
discord.onMessage(function(event)
  if event.authorIsBot then
    return
  end

  if event.matches("!", "hilfe") then
    event.reply("Verfügbare Befehle: `/ping`")
  end
end)
```

`MessageEvent` enthält unter anderem:

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

## Guild Events

```lua
discord.onGuildJoin(function(event)
  logger.info("Neue Guild: " .. event.guildName)
end)

discord.onGuildLeave(function(event)
  logger.info("Guild verlassen: " .. event.guildName)
end)
```

## Komponenten-Events

Komponenten-Events werden über ihre `customId` registriert:

```lua
discord.onButton("confirm", function(event)
  event.replyEphemeral("Bestätigt.")
end)

discord.onSelectMenu("role_select", function(event)
  event.replyEphemeral("Auswahl: " .. event.values[1])
end)

discord.onModalSubmit("feedback", function(event)
  event.replyEphemeral("Danke für dein Feedback.")
end)
```
