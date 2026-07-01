---
title: Storage
description: Store persistent addon data with the safe Storage API.
icon: database
---

## Overview

Use `discord.storage()` to access your addon's default storage. Values remain available across restarts.

```lua
local storage = discord.storage()

local count = storage.increment("uses", 1)
storage.set("last_status", "ok")
```

## Store JSON

```lua
storage.setJson("settings", {
  enabled = true,
  channelId = "1234567890"
})

local settings = storage.getJson("settings", {
  enabled = false
})
```

## Namespaces

Use namespaces for separate areas:

```lua
local userStorage = discord.createStorage("users")
userStorage.set("last_user", "1234567890")
```

## Methods

* `get(key, fallback?)`
* `set(key, value)`
* `put(key, value)`
* `delete(key)`
* `exists(key)`
* `getJson(key, fallback?)`
* `setJson(key, value)`
* `increment(key, amount?)`
* `decrement(key, amount?)`
* `keys(prefix?)`
