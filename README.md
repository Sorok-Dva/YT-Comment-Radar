# Youtube Comments Radar

Bring back like notifications for your own YouTube comments.

`Youtube Comments Radar` is a browser extension for Chrome, Edge, and Firefox that tracks your known YouTube comments, checks their like counts, and notifies you when they go up.

This public repository is a presentation and release hub. It does not include the extension source code.

## Why This Exists

YouTube still keeps a comment history, but it no longer gives a clear built-in flow for "someone liked your comment" in the way many people expect.

This extension rebuilds that missing signal by:

1. importing your known comments from YouTube comment history
2. storing the related `commentId + videoId`
3. reading like counts through the official YouTube Data API
4. detecting increases
5. showing browser notifications and an in-page YouTube likes hub

## Main Features

- Official API-based like scanning
- Comment-history import from YouTube / Google My Activity
- Live sync when you open a video you already commented on
- Dedicated YouTube topbar button with unread badge
- Recent likes panel directly on YouTube
- Multi-account / multi-channel aware tracking
- English / French interface
- Local browser notifications
- No external backend required

## How It Works

The extension uses two different flows:

- Import:
  It reads your YouTube comment history page to discover comments you previously posted.
- Scan:
  It uses the official `YouTube Data API v3` to query comment like counts by comment ID.

Important:

- Like scanning requires your own YouTube API key.
- Comment scanning is API-only.
- DOM/page parsing is kept only for comment-history import.

## Installation

Get the latest build from the repository releases or from the provided browser package, then install it in your browser.

### Chrome / Edge

1. Open the extensions page.
2. Enable developer mode.
3. Click `Load unpacked`.
4. Select the extension build folder.

### Firefox

1. Open `about:debugging`.
2. Choose `This Firefox`.
3. Click `Load Temporary Add-on`.
4. Select the extension `manifest.json`.

## Quick Start

1. Open the extension settings.
2. Add your `YouTube Data API v3` key.
3. Import your YouTube comment history.
4. Run a first scan to establish the initial like counts.
5. Let the extension monitor future changes automatically.

## API Key FAQ

### Where do I create a YouTube API key?

In Google Cloud Console:

1. Create or select a project.
2. Enable `YouTube Data API v3`.
3. Open `APIs & Services > Credentials`.
4. Create an `API key`.

### Why can a brand-new key still return `quotaExceeded`?

Because quota is attached to the Google Cloud project, not to the key itself.

If you create a new key inside a project that already exhausted its YouTube quota, the new key inherits the same exhausted quota.

### Fast fix for quota issues

Create a new Google Cloud project, enable `YouTube Data API v3`, then create a new key in that new project.

### When does quota reset?

The YouTube Data API daily quota resets at midnight Pacific Time.

## Privacy

- Your comment tracking data stays in your browser storage.
- The extension uses your own API key to query YouTube.
- No dedicated external server is required for the core workflow.

## Credits

Designed and developed by **Сорок два**.

- Website: https://p-42.fr/sorokdva-yt
- GitHub profile: https://p-42.fr/github-sorokdva-yt
- Support the project: https://p-42.fr/sorokdva-github-sponsor

If the extension is useful to you, a small donation helps fund maintenance and future improvements.

## Disclaimer

This project is an independent tool and is not affiliated with or endorsed by YouTube or Google.
