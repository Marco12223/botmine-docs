---
title: Presence
description: Set the bot status and activity.
icon: radio_button_checked
---

## Set activity

```lua
discord.setActivity("WATCHING", "over the server")
```

Activity types:

* `PLAYING`
* `WATCHING`
* `LISTENING`
* `STREAMING`
* `COMPETING`

## Set presence

```lua
discord.setPresence({
  status = "ONLINE",
  activity = {
    type = "PLAYING",
    name = "BotMine"
  }
})
```

Online status:

* `ONLINE`
* `IDLE`
* `DO_NOT_DISTURB`
* `INVISIBLE`
* `OFFLINE`

## Clear activity

```lua
discord.clearActivity()
```
