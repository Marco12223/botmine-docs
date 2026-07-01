---
title: HTTP
description: Call external APIs through the safe HTTP wrapper of the Lua SDK.
icon: public
---

## Overview

The SDK provides HTTP methods through `discord`. Use these wrappers instead of direct network access.

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

## Methods

* `request(method, url, options?)`
* `get(url, options?)`
* `post(url, body?, options?)`
* `put(url, body?, options?)`
* `patch(url, body?, options?)`
* `delete(url, options?)`

## Request options

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

Options:

* `headers`
* `body`
* `timeoutSeconds`
* `query`

## Response

`HttpResponse` contains:

* `status`
* `ok`
* `body`
* `headers`
* `json()`
