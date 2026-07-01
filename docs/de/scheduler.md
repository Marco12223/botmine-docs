---
title: Scheduler
description: Plane einmalige und wiederkehrende Tasks.
icon: schedule
---

## Einmaliger Task

```lua
scheduler.setTimeout(function()
  logger.info("Task ausgeführt")
end, 5000)
```

Die Zeit wird in Millisekunden angegeben.

## Wiederkehrender Task

```lua
local taskId = scheduler.setInterval(function()
  logger.debug("Heartbeat")
end, 60000)
```

## Task abbrechen

```lua
scheduler.cancel(taskId)
```

## Methoden

* `setTimeout(callback, delayMillis)`
* `setInterval(callback, intervalMillis)`
* `cancel(taskId)`
