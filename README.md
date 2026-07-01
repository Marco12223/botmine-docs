# BotMine Documentation

This repository contains the public documentation for BotMine addon development. It covers the creator workflow for publishing addons and the Lua SDK used by addons at runtime.

## Contents

The documentation is available in German and English:

```text
docs/
├── de/
│   ├── overview.md
│   ├── addons-hochladen.md
│   ├── lua-sdk.md
│   ├── messages-embeds.md
│   ├── events.md
│   ├── slash-commands.md
│   ├── interactions.md
│   ├── guilds-members.md
│   ├── channels-threads.md
│   ├── config.md
│   ├── storage.md
│   ├── http.md
│   ├── scheduler.md
│   ├── logging-json.md
│   ├── permissions.md
│   ├── presence.md
│   └── nav.json
└── en/
    ├── overview.md
    ├── upload-addons.md
    ├── lua-sdk.md
    ├── messages-embeds.md
    ├── events.md
    ├── slash-commands.md
    ├── interactions.md
    ├── guilds-members.md
    ├── channels-threads.md
    ├── config.md
    ├── storage.md
    ├── http.md
    ├── scheduler.md
    ├── logging-json.md
    ├── permissions.md
    ├── presence.md
    └── nav.json
```

## Documentation Areas

The docs are split into focused pages:

* **Getting started**: overview and addon upload/review workflow.
* **Lua SDK basics**: global APIs and fixed SDK values.
* **Discord features**: messages, embeds, events, slash commands, interactions, channels, guilds, and members.
* **Addon runtime APIs**: config, storage, HTTP, scheduler, logging, JSON, permissions, and presence.

## Navigation

Each language has its own `nav.json`. When adding or renaming a page, update the matching navigation file:

* `docs/de/nav.json`
* `docs/en/nav.json`

The `slug` value must match the Markdown filename without the `.md` extension.

## Writing Guidelines

Keep pages practical and focused:

* Write in clear, direct language.
* Prefer short examples that can be copied into a Lua addon.
* Keep German and English docs structurally aligned where possible.
* Document required permissions when an example performs privileged Discord actions.
* Avoid documenting APIs that are not exposed by the BotMine Lua SDK.

## Validation

There is currently no dedicated build or test script in this repository. At minimum, validate navigation JSON before committing:

```bash
python3 -m json.tool docs/de/nav.json
python3 -m json.tool docs/en/nav.json
```
