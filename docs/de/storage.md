---
title: Storage
description: Speichere persistente Addon-Daten mit dem sicheren Storage API.
icon: database
---

## Überblick

Mit `discord.storage()` erhältst du den Standard-Storage deines Addons. Werte bleiben über Neustarts hinweg erhalten.

```lua
local storage = discord.storage()

local count = storage.increment("uses", 1)
storage.set("last_status", "ok")
```

## JSON speichern

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

Für getrennte Bereiche kannst du eigene Namespaces verwenden:

```lua
local userStorage = discord.createStorage("users")
userStorage.set("last_user", "1234567890")
```

## Methoden

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
