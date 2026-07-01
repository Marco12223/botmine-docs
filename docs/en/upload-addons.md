---
title: Upload Addons
description: Prepare a BotMine addon, upload a ZIP build, and submit it for review.
icon: upload
---

## Overview

This guide explains how to prepare your own BotMine addon, upload it in the dashboard, and submit it for review. Addons are saved privately as drafts first. They only become public after staff approval.

## Requirements

You need:

* a BotMine account
* a clear addon name
* a short description for lists and cards
* a longer description for the detail page
* a matching category
* a version, for example `1.0.0`
* a ZIP build if the addon should be installable
* optionally a thumbnail as `png`, `jpg`, `jpeg`, `webp`, or `gif`

## Create an addon

Open:

```text
Dashboard > Addons > New Addon
```

Direct path:

```text
/dashboard/addons/new
```

Fill in the addon data:

* `Name`: visible addon name
* `Short description`: a short sentence that is easy to scan in the Marketplace
* `Description`: purpose, target audience, and included features
* `Category`: matching addon category
* `Version`: current addon version
* `Thumbnail`: optional image for Marketplace and detail page
* `Config Schema`: optional configuration fields for bot installations
* `Permissions`: runtime permissions required by your addon
* `Addon ZIP`: optional first build

When you save, the addon is created as a private draft. It is not public yet.

## Prepare the ZIP build

The addon is uploaded as a ZIP. The ZIP must be safe and clearly structured.

Allowed:

* ZIP file up to 50 MB
* at most 1000 files in the ZIP
* unpacked total size up to 100 MB
* individual files up to 25 MB
* manifest file `addon.yml` or `addon.yaml`

Not allowed:

* paths containing `../`
* absolute paths
* symlinks
* ZIP64 builds
* missing or unreadable manifest file

## Manifest

Every build needs an `addon.yml` or `addon.yaml`.

Required fields:

```yaml
id: your-addon-id
name: My Addon
version: 1.0.0
entry: index.lua
```

Notes:

* `id` is internally adjusted to the BotMine addon UUID during upload.
* `entry` must point to a file that exists inside the ZIP.
* These Lua docs use `index.lua` as an example. What matters is the actual file name in your ZIP.
* The manifest may be in the ZIP root or inside one single project folder.

Example with manifest in the root:

```text
my-addon.zip
├── addon.yml
├── index.lua
└── package.json
```

Example with one project folder:

```text
my-addon.zip
└── my-addon/
    ├── addon.yml
    ├── index.lua
    └── package.json
```

## Upload more builds

After creating the addon, you can manage builds on the addon detail page.

Typical path:

```text
/dashboard/addons/{addonId}/builds
```

Each uploaded build is stored privately and is only available to authorized users, the creator, or staff.

## Submit for review

When your addon is ready:

1. Open the addon detail page.
2. Check name, description, category, version, config, and permissions.
3. Upload at least the build that should be reviewed.
4. Click `Submit for review`.

The addon receives this status:

```text
IN_REVIEW
```

During review, it is still not publicly visible.

## Staff review

Staff checks:

* description and presentation
* category and Marketplace fit
* ZIP build and manifest
* runtime permissions
* security and obvious abuse risks
* whether the addon is installable and understandable

Possible results:

* `PUBLISHED`: the addon was approved and can become visible.
* `DRAFT` or `HIDDEN`: the addon must be revised.
* `DISABLED` or `ARCHIVED`: the addon is not usable or was removed.

## Updates after publishing

If you edit an already published addon, it is removed from visibility and moved back into the review process.

This matters because updates can change code, permissions, description, or behavior.

## Write a good description

A good addon description answers:

* What does the addon do?
* Which problem does it solve?
* Which Discord servers is it meant for?
* Which configuration is required?
* Which permissions does it need?
* Are there known limits?

Avoid:

* vague marketing copy without concrete features
* false promises
* external downloads outside BotMine
* hidden or unexplained permissions

## Submission checklist

* Addon has a clear name.
* Short description is understandable.
* Description explains features and usage.
* Category matches.
* Version is set.
* ZIP contains `addon.yml` or `addon.yaml`.
* Manifest contains `id`, `name`, `version`, and `entry`.
* The `entry` file exists inside the ZIP.
* ZIP has no unsafe paths or symlinks.
* Permissions are complete and understandable.
* Config Schema is valid or empty.
* The build is the build that should be reviewed.

## Upload errors

Common causes:

* ZIP is missing.
* File is not a ZIP.
* ZIP is too large.
* `addon.yml` is missing.
* Manifest fields are missing.
* `entry` points to a file that does not exist.
* ZIP contains unsafe paths.
* ZIP contains symlinks.

If an upload fails, fix the build locally and upload a new ZIP.

## Visibility

Privately saved addons are only visible to you and authorized staff areas.

An addon only becomes public when staff has approved it and it is marked as visible. You can add your own addons to your bots without a purchased entitlement if the platform recognizes you as the creator.
