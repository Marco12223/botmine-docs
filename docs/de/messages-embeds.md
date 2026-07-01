---
title: Nachrichten & Embeds
description: Sende, bearbeite und lösche Discord-Nachrichten mit dem Lua SDK.
icon: chat
---

## Nachrichten

```lua
discord.sendMessage(channelId, "Hallo!")
discord.replyToMessage(channelId, messageId, "Antwort")
discord.editMessage(channelId, messageId, "Neue Nachricht")
discord.deleteMessage(channelId, messageId)
```

Wichtige Methoden:

* `sendMessage(channelId, content)`
* `editMessage(channelId, messageId, content)`
* `deleteMessage(channelId, messageId)`
* `replyToMessage(channelId, messageId, content)`

## Embeds

```lua
local embed = discord.embed()
  :setTitle("Status")
  :setDescription("Alles läuft.")
  :setColor("#22c55e")

discord.sendEmbed(channelId, embed)
```

Embed-Builder:

* `setTitle(title, url?)`
* `setDescription(description)`
* `setColor(color)`
* `setUrl(url)`
* `setTimestamp(timestamp?)`
* `setFooter(text, iconUrl?)`
* `setImage(url)`
* `setThumbnail(url)`
* `setAuthor(name, url?, iconUrl?)`
* `addField(name, value, inline?)`
* `clearFields()`
* `build()`

## Message Builder

```lua
local message = discord.message()
  :setContent("Wähle eine Aktion")
  :addEmbed(embed)
  :addButton(discord.button("confirm", "Bestätigen", "SUCCESS"))
  :build()

discord.sendMessage(channelId, message)
```

Message-Builder:

* `setContent(content)`
* `addEmbed(embed)`
* `setEmbeds(embeds)`
* `addActionRow(components)`
* `addButton(button)`
* `addSelectMenu(menu)`
* `setAllowedMentions(allowed)`
* `build()`
