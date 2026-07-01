---
title: HTTP
description: Rufe externe APIs über den sicheren HTTP-Wrapper des Lua SDK auf.
icon: public
---

## Überblick

Das SDK stellt HTTP-Methoden über `discord` bereit. Verwende diese Wrapper statt direkter Netzwerkzugriffe.

```lua
local response = discord.get("https://api.example.com/status", {
  timeoutSeconds = 10,
  headers = {
    ["Accept"] = "application/json"
  }
})

if response.ok then
  local data = response.json()
  logger.info(json.encode(data))
end
```

## Methoden

* `request(method, url, options?)`
* `get(url, options?)`
* `post(url, body?, options?)`
* `put(url, body?, options?)`
* `patch(url, body?, options?)`
* `delete(url, options?)`

## Request Options

```lua
local response = discord.post("https://api.example.com/events", {
  event = "install",
  addon = config.addonId
}, {
  timeoutSeconds = 10,
  headers = {
    ["Content-Type"] = "application/json"
  },
  query = {
    source = "botmine"
  }
})
```

Optionen:

* `headers`
* `body`
* `timeoutSeconds`
* `query`

## Response

`HttpResponse` enthält:

* `status`
* `ok`
* `body`
* `headers`
* `json()`
