---
title: Guilds & Members
description: Read guild, user, and member data and run role or moderation actions.
icon: groups
---

## Read objects

```lua
local guild = discord.getGuild(guildId)
local user = discord.getUser(userId)
local member = discord.getMember(guildId, userId)
```

Methods:

* `getGuild(guildId)`
* `getUser(userId)`
* `getMember(guildId, userId)`

## Roles

```lua
discord.addRole(guildId, userId, roleId, "Addon rule")
discord.removeRole(guildId, userId, roleId, "Addon rule")
```

Member objects also provide role methods:

```lua
if member ~= nil then
  member.addRole(roleId, "Setup")
end
```

## Moderation

```lua
discord.timeoutMember(guildId, userId, 600, "Spam")
discord.removeTimeout(guildId, userId, "Manually removed")
discord.kickMember(guildId, userId, "Rule violation")
discord.banMember(guildId, userId, 0, "Rule violation")
discord.unbanUser(guildId, userId, "Unbanned")
```

Methods:

* `timeoutMember(guildId, userId, seconds, reason?)`
* `removeTimeout(guildId, userId, reason?)`
* `kickMember(guildId, userId, reason?)`
* `banMember(guildId, userId, deleteMessageSeconds?, reason?)`
* `unbanUser(guildId, userId, reason?)`

## Check permissions

```lua
if discord.hasPermission(guildId, userId, "MANAGE_MESSAGES") then
  discord.deleteMessage(channelId, messageId)
end
```
