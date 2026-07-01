---
title: Messages & Embeds
description: Send, edit, and delete Discord messages with the Lua SDK.
icon: chat
---

## Messages

```lua
discord.sendMessage(channelId, "Hello!")
discord.replyToMessage(channelId, messageId, "Reply")
discord.editMessage(channelId, messageId, "Updated message")
discord.deleteMessage(channelId, messageId)
```

Methods:

* `sendMessage(channelId, content)`
* `editMessage(channelId, messageId, content)`
* `deleteMessage(channelId, messageId)`
* `replyToMessage(channelId, messageId, content)`

## Embeds

```lua
local embed = discord.embed()
  :setTitle("Status")
  :setDescription("Everything is running.")
  :setColor("#22c55e")

discord.sendEmbed(channelId, embed)
```

Embed builder:

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

## Message builder

```lua
local message = discord.message()
  :setContent("Choose an action")
  :addEmbed(embed)
  :addButton(discord.button("confirm", "Confirm", "SUCCESS"))
  :build()

discord.sendMessage(channelId, message)
```

Message builder:

* `setContent(content)`
* `addEmbed(embed)`
* `setEmbeds(embeds)`
* `addActionRow(components)`
* `addButton(button)`
* `addSelectMenu(menu)`
* `setAllowedMentions(allowed)`
* `build()`
