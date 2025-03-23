---
layout: post
title: How to Install Extensions on Ungoogled Chromium (e.g., Strongbox Autofill)
date: 2025-03-23
category: productivity
author: 
tags: [macos, chromium]
summary: 
---

Ungoogled Chromium is a privacy-focused alternative to Google Chrome. While it offers the speed and compatibility of Chromium, it removes all background connections to Google services. This means:

- No automatic sign-ins or telemetry.
- No Google sync or profile linking.
- A much cleaner privacy baseline out of the box.

If you're concerned about data collection or want a browser that respects your independence from the Google ecosystem, Ungoogled Chromium is a strong alternative.

## Installing Ungoogled Chromium on macOS

If you're using [Homebrew](https://brew.sh), installing Ungoogled Chromium is easy:

```bash
brew install eloston-chromium
```

## The Problem with Extensions

Ungoogled Chromium doesn’t allow installing extensions directly from the Chrome Web Store by default. This is part of its design: no automatic connections to Google means no direct Web Store access.

For example, if you try to install the Strongbox Autofill extension, you’ll see something like this:

> “Extension disabled” or “Apps, extensions, and user scripts cannot be added from this website.”

But don’t worry—you can still install extensions manually.

## Steps to Manually Install Extensions

### Step 1: Install the Chromium Web Store Extension

This lets you install extensions from the Chrome Web Store, bypassing the default block in Ungoogled Chromium.
1. Visit this mirror of the Chromium Web Store extension:
https://github.com/NeverDecaf/chromium-web-store
2. Click the green Code > Download ZIP button, then extract the ZIP file.
3. In Ungoogled Chromium:
   * Navigate to chrome://extensions/
   * Enable Developer mode (top right toggle).
   * Click Load unpacked, and select the folder you just extracted.

Now you’ll see the “Add to Chromium” button enabled again on extension pages.

### Step 2: Install the Desired Extension

Go to the Strongbox Autofill extension page. With the Chromium Web Store extension installed, the “Add to Chromium” button should now work.

Click it to install Strongbox Autofill just like on regular Chrome.

### Step 3: Confirm and Pin the Extension
* Head back to `chrome://extensions/` to confirm it’s installed and enabled.
* Optionally, pin the extension to your toolbar for quick access.

