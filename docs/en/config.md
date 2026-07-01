---
title: Config
description: Read addon configuration and schema information.
icon: tune
---

## Overview

Configuration is available through `config` and `discord.config`. It contains values set for a bot installation.

```lua
local logChannelId = config:get("log_channel")
local requiredValue = config:require("api_key")

if config:has("enabled") then
  logger.info("Addon is configured.")
end
```

## Methods

* `get(key, fallback?)`
* `require(key)`
* `has(key)`
* `all()`
* `schema()`

## Fallbacks

```lua
local prefix = config:get("prefix", "!")
```

## Read schema

```lua
local schema = config:schema()

for index = 1, #schema do
  logger.debug(schema[index].key)
end
```
