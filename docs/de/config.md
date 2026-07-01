---
title: Config
description: Lies Addon-Konfigurationen und Schema-Informationen aus.
icon: tune
---

## Überblick

Die Konfiguration ist über `config` und `discord.config` erreichbar. Sie enthält Werte, die für eine Bot-Installation gesetzt wurden.

```lua
local logChannelId = config:get("log_channel")
local requiredValue = config:require("api_key")

if config:has("enabled") then
  logger.info("Addon ist konfiguriert.")
end
```

## Methoden

* `get(key, fallback?)`
* `require(key)`
* `has(key)`
* `all()`
* `schema()`

## Fallbacks

```lua
local prefix = config:get("prefix", "!")
```

## Schema lesen

```lua
local schema = config:schema()

for index = 1, #schema do
  logger.debug(schema[index].key)
end
```
