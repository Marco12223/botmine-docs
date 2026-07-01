---
title: Permissions
description: Document and check runtime permissions for your addon.
icon: admin_panel_settings
---

## Overview

Permissions describe which Discord actions an addon may perform. Request only permissions your addon actually needs, and explain them clearly in the addon description.

## Available permissions

* `ADMINISTRATOR`
* `MANAGE_SERVER`
* `MANAGE_CHANNEL`
* `MANAGE_ROLES`
* `MANAGE_MESSAGES`
* `KICK_MEMBERS`
* `BAN_MEMBERS`
* `MODERATE_MEMBERS`
* `VIEW_CHANNEL`
* `SEND_MESSAGES`
* `EMBED_LINKS`
* `ATTACH_FILES`
* `ADD_REACTIONS`
* `USE_APPLICATION_COMMANDS`
* `CONNECT`
* `SPEAK`
* `MOVE_MEMBERS`
* `MUTE_MEMBERS`
* `DEAFEN_MEMBERS`

## Check permissions

```lua
if not event.hasPermission("MANAGE_MESSAGES") then
  event.replyEphemeral("You do not have permission for that.")
  return
end

event.reply("You can manage messages.")
```

Directly through the Discord API:

```lua
if discord.hasPermission(guildId, userId, "MANAGE_ROLES") then
  discord.addRole(guildId, userId, roleId, "Role action")
end
```
