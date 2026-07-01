---
title: BotMine Addon Development
description: Develop, package, and publish secure BotMine addons.
icon: rocket_launch
---

## Overview

BotMine addons extend bots with custom functionality without requiring direct access to the Discord API or sensitive infrastructure. Addons run in a controlled Lua environment and use the BotMine Lua SDK as a safe interface for messages, slash commands, interactions, configuration, storage, HTTP, and logging.

This documentation is for creators who want to build, test, and publish their own addons in the BotMine Marketplace.

## What you can build

An addon can:

* react to messages and events
* register slash commands
* use embeds, buttons, select menus, and modals
* assign roles or run moderation actions
* store persistent data in addon storage
* call external APIs through the safe HTTP wrapper
* provide configurable fields for bot installations

Which actions an addon may perform depends on the requested permissions and the platform review.

## Typical workflow

1. Develop the addon locally.
2. Create an `addon.yml` or `addon.yaml` manifest.
3. Package the addon files as a ZIP.
4. Create the addon in the dashboard.
5. Upload the ZIP build.
6. Submit the addon for review.
7. After approval, the addon can be published in the Marketplace.

## Important files

Every publishable build needs a manifest. The manifest must describe at least the ID, name, version, and entry file.

```yaml
id: my-addon
name: My Addon
version: 1.0.0
entry: index.lua
```

The `entry` value must point to a file that exists inside the ZIP. During upload, the `id` is internally adjusted to the BotMine addon UUID.

## Next steps

Start with the guide for uploading and submitting addons. Then use the SDK pages to look up messages, events, storage, HTTP requests, and the other Lua APIs.
