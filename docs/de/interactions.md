---
title: Interaktionen
description: Nutze Buttons, Link-Buttons, Select Menus und Modals.
icon: touch_app
---

## Buttons

```lua
local button = discord.button("confirm", "Bestätigen", "SUCCESS")

discord.onButton("confirm", function(event)
  event.replyEphemeral("Bestätigt.")
end)
```

Button-Styles:

* `PRIMARY`
* `SECONDARY`
* `SUCCESS`
* `DANGER`
* `LINK`

Für externe Links:

```lua
local button = discord.linkButton("https://botmine.example", "BotMine öffnen")
```

## Select Menus

```lua
local menu = discord.selectMenu("role_select", "Rolle auswählen")
  :addOption("Support", "support")
  :addOption("News", "news")

discord.onSelectMenu("role_select", function(event)
  event.replyEphemeral("Auswahl: " .. event.values[1])
end)
```

Select-Menu-Builder:

* `setPlaceholder(placeholder)`
* `setMinValues(min)`
* `setMaxValues(max)`
* `setDisabled(disabled)`
* `addOption(label, value, description?, emoji?)`
* `build()`

## Modals

```lua
local modal = discord.modal("feedback", "Feedback")
  :addTextInput("message", "Nachricht", "PARAGRAPH", {
    required = true,
    maxLength = 1000
  })

discord.onModalSubmit("feedback", function(event)
  local message = event.getValue("message", "")
  event.replyEphemeral("Danke für dein Feedback.")
end)
```

Text-Input-Styles:

* `SHORT`
* `PARAGRAPH`
