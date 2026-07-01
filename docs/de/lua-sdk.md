---
title: Lua SDK Grundlagen
description: Überblick über die globalen APIs und festen Typwerte des BotMine Lua SDK.
icon: code
---

## Überblick

Das BotMine Lua SDK stellt sichere globale APIs bereit, mit denen Addons Discord-Funktionen nutzen können, ohne direkt unsichere Runtime-Zugriffe zu benötigen.

Verfügbare Globals:

* `discord`: Discord API Wrapper, Events, Slash Commands, Nachrichten, Komponenten, Guild- und Member-Aktionen
* `config`: Addon-Konfiguration
* `logger`: Logging
* `json`: JSON Encode und Decode
* `scheduler`: Timer und wiederkehrende Tasks

## Erstes Beispiel

```lua
discord.onReady(function(event)
  logger.info("Addon gestartet als " .. event.botName)
end)

discord.slashCommand("ping", "Antwortet mit Pong", function(event)
  event.reply("Pong!")
end)
```

## Feste Typwerte

Viele SDK-Methoden erwarten feste String-Werte. Diese Werte sind case-sensitiv.

Channel-Typen:

* `TEXT`
* `VOICE`
* `CATEGORY`
* `NEWS`
* `STAGE`
* `FORUM`
* `THREAD_PUBLIC`
* `THREAD_PRIVATE`
* `THREAD_NEWS`

Button-Styles:

* `PRIMARY`
* `SECONDARY`
* `SUCCESS`
* `DANGER`
* `LINK`

Text-Input-Styles:

* `SHORT`
* `PARAGRAPH`

Activity-Typen:

* `PLAYING`
* `WATCHING`
* `LISTENING`
* `STREAMING`
* `COMPETING`

Online-Status:

* `ONLINE`
* `IDLE`
* `DO_NOT_DISTURB`
* `INVISIBLE`
* `OFFLINE`

Thread Auto-Archive-Dauer:

* `60`
* `1440`
* `4320`
* `10080`
