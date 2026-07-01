---
title: Logging & JSON
description: Schreibe Logs und arbeite mit JSON-Daten.
icon: data_object
---

## Logging

```lua
logger.info("Info")
logger.warn("Warnung")
logger.error("Fehler")
logger.debug("Debug")
```

Nutze Logs, um Addon-Zustand, Fehler und Review-relevantes Verhalten nachvollziehbar zu machen.

## JSON

```lua
local encoded = json.encode({
  ok = true,
  count = 3
})

local decoded = json.decode(encoded)
```

Methoden:

* `json.encode(value)`
* `json.decode(value)`
