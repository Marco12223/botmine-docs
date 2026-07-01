---
title: Lua SDK Basics
description: Overview of the global APIs and fixed type values in the BotMine Lua SDK.
icon: code
---

## Overview

The BotMine Lua SDK provides safe global APIs so addons can use Discord functionality without direct unsafe runtime access.

Available globals:

* `discord`: Discord API wrapper, events, slash commands, messages, components, guild and member actions
* `config`: addon configuration
* `logger`: logging
* `json`: JSON encode and decode
* `scheduler`: timers and recurring tasks

## First example

```lua
discord.onReady(function(event)
  logger.info("Addon started as " .. event.botName)
end)

discord.slashCommand("ping", "Replies with Pong", function(event)
  event.reply("Pong!")
end)
```

## Fixed type values

Many SDK methods expect fixed string values. These values are case-sensitive.

Channel types:

* `TEXT`
* `VOICE`
* `CATEGORY`
* `NEWS`
* `STAGE`
* `FORUM`
* `THREAD_PUBLIC`
* `THREAD_PRIVATE`
* `THREAD_NEWS`

Button styles:

* `PRIMARY`
* `SECONDARY`
* `SUCCESS`
* `DANGER`
* `LINK`

Text input styles:

* `SHORT`
* `PARAGRAPH`

Activity types:

* `PLAYING`
* `WATCHING`
* `LISTENING`
* `STREAMING`
* `COMPETING`

Online status:

* `ONLINE`
* `IDLE`
* `DO_NOT_DISTURB`
* `INVISIBLE`
* `OFFLINE`

Thread auto archive duration:

* `60`
* `1440`
* `4320`
* `10080`
