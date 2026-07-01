---
title: Presence
description: Setze Status und Activity des Bots.
icon: radio_button_checked
---

## Activity setzen

```lua
discord.setActivity("WATCHING", "über den Server")
```

Activity-Typen:

* `PLAYING`
* `WATCHING`
* `LISTENING`
* `STREAMING`
* `COMPETING`

## Presence setzen

```lua
discord.setPresence({
  status = "ONLINE",
  activity = {
    type = "PLAYING",
    name = "BotMine"
  }
})
```

Online-Status:

* `ONLINE`
* `IDLE`
* `DO_NOT_DISTURB`
* `INVISIBLE`
* `OFFLINE`

## Activity entfernen

```lua
discord.clearActivity()
```
