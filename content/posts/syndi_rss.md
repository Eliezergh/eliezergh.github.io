+++ 
draft = false
date = 2025-11-30T19:17:59Z
title = "Syndi - A lightweight RSS notifier for macOS"
description = "A simple menu bar app to keep track of your favorite RSS feeds"
tags = ["macos", "python", "rss", "open-source"]
categories = ["Projects"]
+++

I've just released **Syndi**, a lightweight macOS menu bar application that notifies you when your favorite RSS feeds have new content.

## Why Syndi?

I wanted a simple, no-frills way to stay updated on RSS feeds without having to open a browser or a dedicated RSS reader. Syndi lives quietly in your menu bar and sends native macOS notifications when new articles are published.

## Features

- **Menu Bar App** - Lives in your macOS menu bar, stays out of the way
- **Native Notifications** - Get macOS notifications for new posts
- **Quick Access** - Click recent items to open posts directly in your browser
- **Simple Configuration** - Easy JSON-based configuration for your feeds
- **Auto-Check** - Periodically checks feeds in the background
- **Smart Tracking** - Remembers what you've seen to avoid duplicate notifications
- **Standalone** - Bundles into a native `.app` with no Python installation required

## Tech Stack

Syndi is built with Python and uses:
- **rumps** - For the macOS menu bar integration
- **feedparser** - For RSS/Atom feed parsing
- **py2app** - To bundle everything into a native macOS application

## Installation

The easiest way to get started is to download the pre-built app from the [GitHub Releases](https://github.com/Eliezergh/Syndi/releases) page:

1. Download `Syndi-vX.X.X-macos.zip`
2. Unzip and drag `Syndi.app` to your Applications folder
3. Right-click → **Open** on first launch (to bypass Gatekeeper)
4. Configure your feeds in `~/.syndi/config.json`

## Configuration

The configuration is straightforward - just edit `~/.syndi/config.json`:

```json
{
  "feeds": [
    {
      "name": "Hacker News",
      "url": "https://news.ycombinator.com/rss",
      "enabled": true
    },
    {
      "name": "GitHub Blog",
      "url": "https://github.blog/feed/",
      "enabled": true
    }
  ],
  "check_interval_seconds": 300,
  "notification_enabled": true,
  "max_recent_items": 10
}
```

## Open Source

Syndi is open source and available on GitHub under the MIT license. Feel free to contribute, report issues, or fork it for your own needs!

**GitHub Repository:** [github.com/Eliezergh/Syndi](https://github.com/Eliezergh/Syndi)
