---
title: Slash Commands
description: Registriere Slash Commands und lies Optionen aus.
icon: terminal
---

## Einfacher Command

```lua
discord.slashCommand("ping", "Antwortet mit Pong", function(event)
  event.reply("Pong!")
end)
```

## Optionen

```lua
discord.slashCommand("avatar", "Zeigt den Avatar eines Users", function(event)
  local user = event.getUser("user") or event.user
  event.reply(user.avatarUrl or "Kein Avatar gefunden.")
end)
:addUserOption("user", "User", false)
```

Option-Typen:

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

## Command-Objekt

```lua
discord.registerSlashCommand({
  name = "say",
  description = "Sendet eine Nachricht",
  options = {
    {
      name = "text",
      description = "Nachricht",
      type = "STRING",
      required = true
    }
  }
}, function(event)
  event.reply(event.getString("text", ""))
end)
```

## Antworten

`SlashCommandEvent` bietet:

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
