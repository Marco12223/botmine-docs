---
title: Scheduler
description: Schedule one-time and recurring tasks.
icon: schedule
---

## One-time task

```lua
scheduler.setTimeout(function()
  logger.info("Task executed")
end, 5000)
```

The delay is given in milliseconds.

## Recurring task

```lua
local taskId = scheduler.setInterval(function()
  logger.debug("Heartbeat")
end, 60000)
```

## Cancel a task

```lua
scheduler.cancel(taskId)
```

## Methods

* `setTimeout(callback, delayMillis)`
* `setInterval(callback, intervalMillis)`
* `cancel(taskId)`
