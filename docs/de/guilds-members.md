---
title: Guilds & Member
description: Lies Guild-, User- und Member-Daten und führe Rollen- oder Moderationsaktionen aus.
icon: groups
---

## Objekte lesen

```lua
local guild = discord.getGuild(guildId)
local user = discord.getUser(userId)
local member = discord.getMember(guildId, userId)
```

Methoden:

* `getGuild(guildId)`
* `getUser(userId)`
* `getMember(guildId, userId)`

## Rollen

```lua
discord.addRole(guildId, userId, roleId, "Addon-Regel")
discord.removeRole(guildId, userId, roleId, "Addon-Regel")
```

Member-Objekte bieten ebenfalls Rollenmethoden:

```lua
if member ~= nil then
  member.addRole(roleId, "Setup")
end
```

## Moderation

```lua
discord.timeoutMember(guildId, userId, 600, "Spam")
discord.removeTimeout(guildId, userId, "Manuell aufgehoben")
discord.kickMember(guildId, userId, "Regelverstoß")
discord.banMember(guildId, userId, 0, "Regelverstoß")
discord.unbanUser(guildId, userId, "Entbannt")
```

Methoden:

* `timeoutMember(guildId, userId, seconds, reason?)`
* `removeTimeout(guildId, userId, reason?)`
* `kickMember(guildId, userId, reason?)`
* `banMember(guildId, userId, deleteMessageSeconds?, reason?)`
* `unbanUser(guildId, userId, reason?)`

## Permissions prüfen

```lua
if discord.hasPermission(guildId, userId, "MANAGE_MESSAGES") then
  discord.deleteMessage(channelId, messageId)
end
```
