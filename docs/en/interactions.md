---
title: Interactions
description: Use buttons, link buttons, select menus, and modals.
icon: touch_app
---

## Buttons

```lua
local button = discord.button("confirm", "Confirm", "SUCCESS")

discord.onButton("confirm", function(event)
  event.replyEphemeral("Confirmed.")
end)
```

Button styles:

* `PRIMARY`
* `SECONDARY`
* `SUCCESS`
* `DANGER`
* `LINK`

For external links:

```lua
local button = discord.linkButton("https://botmine.example", "Open BotMine")
```

## Select menus

```lua
local menu = discord.selectMenu("role_select", "Select role")
  :addOption("Support", "support")
  :addOption("News", "news")

discord.onSelectMenu("role_select", function(event)
  event.replyEphemeral("Selected: " .. event.values[1])
end)
```

Select menu builder:

* `setPlaceholder(placeholder)`
* `setMinValues(min)`
* `setMaxValues(max)`
* `setDisabled(disabled)`
* `addOption(label, value, description?, emoji?)`
* `build()`

## Modals

```lua
local modal = discord.modal("feedback", "Feedback")
  :addTextInput("message", "Message", "PARAGRAPH", {
    required = true,
    maxLength = 1000
  })

discord.onModalSubmit("feedback", function(event)
  local message = event.getValue("message", "")
  event.replyEphemeral("Thanks for your feedback.")
end)
```

Text input styles:

* `SHORT`
* `PARAGRAPH`
