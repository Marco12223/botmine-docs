---
title: Permissions
description: Dokumentiere und prüfe Runtime-Berechtigungen deines Addons.
icon: admin_panel_settings
---

## Überblick

Permissions beschreiben, welche Discord-Aktionen ein Addon ausführen darf. Fordere nur Rechte an, die dein Addon wirklich benötigt, und erkläre sie in der Addon-Beschreibung nachvollziehbar.

## Verfügbare Permissions

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

## Permissions prüfen

```lua
if not event.hasPermission("MANAGE_MESSAGES") then
  event.replyEphemeral("Dafür fehlt dir die Berechtigung.")
  return
end

event.reply("Du darfst Nachrichten verwalten.")
```

Direkt über die Discord API:

```lua
if discord.hasPermission(guildId, userId, "MANAGE_ROLES") then
  discord.addRole(guildId, userId, roleId, "Rollenaktion")
end
```
