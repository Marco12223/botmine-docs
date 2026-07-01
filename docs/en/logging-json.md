---
title: Logging & JSON
description: Write logs and work with JSON data.
icon: data_object
---

## Logging

```lua
logger.info("Info")
logger.warn("Warning")
logger.error("Error")
logger.debug("Debug")
```

Use logs to make addon state, errors, and review-relevant behavior understandable.

## JSON

```lua
local encoded = json.encode({
  ok = true,
  count = 3
})

local decoded = json.decode(encoded)
```

Methods:

* `json.encode(value)`
* `json.decode(value)`
