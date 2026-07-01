---
title: Slash Commands
description: Register slash commands and read options.
icon: terminal
---

## Simple command

```lua
discord.slashCommand("ping", "Replies with Pong", function(event)
  event.reply("Pong!")
end)
```

## Options

```lua
discord.slashCommand("avatar", "Shows a user's avatar", function(event)
  local user = event.getUser("user") or event.user
  event.reply(user.avatarUrl or "No avatar found.")
end)
:addUserOption("user", "User", false)
```

Option types:

* `STRING`
* `INTEGER`
* `NUMBER`
* `BOOLEAN`
* `USER`
* `MEMBER`
* `CHANNEL`
* `ROLE`
* `MENTIONABLE`
* `ATTACHMENT`

## Command object

```lua
discord.registerSlashCommand({
  name = "say",
  description = "Sends a message",
  options = {
    {
      name = "text",
      description = "Message",
      type = "STRING",
      required = true
    }
  }
}, function(event)
  event.reply(event.getString("text", ""))
end)
```

## Replies

`SlashCommandEvent` provides:

* `reply(content)`
* `replyEphemeral(content)`
* `deferReply(ephemeral?)`
* `editReply(content)`
* `followUp(content, ephemeral?)`
* `showModal(modal)`
* `replyWithButtons(content, buttons)`
* `replyWithButtonsEphemeral(content, buttons)`
* `replyEmbedWithButtons(embed, buttons)`
* `replyEmbedWithButtonsEphemeral(embed, buttons)`
