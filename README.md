# Paisa — Expense Tracker PWA

A mobile-first personal expense tracker. The app interface and logic live in `index.html`; the manifest and service worker provide installability and offline app-shell caching.

## Features

- Home dashboard: monthly, daily, weekly, last-30-day and all-time spending
- Week, month and custom-date reports
- Daily spending bars and category breakdowns
- Add, edit, search, filter and delete expenses
- Five-second undo after deleting an expense
- Custom categories
- JSON backup/restore and CSV export
- INR formatting and responsive light/dark appearance
- Local browser storage; no account or external analytics

## Run locally

Service workers and install prompts require a secure context (`https://` or `localhost`); opening `index.html` directly as a `file://` URL will not enable offline caching.

With Python installed, open a terminal in this folder and run:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` in your browser. Test adding an expense, editing, reporting, export/import and offline mode.

## Install on Android

1. Deploy these files to a static host with HTTPS (for example, a static site host you control).
2. Open the HTTPS site in Chrome on Android.
3. Use Chrome's menu → **Install app** or **Add to Home screen** (the exact wording varies).
4. Open the installed app once online so its app shell can be cached, then test offline.

## APK

A PWA is not automatically an APK. If you specifically need an APK, you can use a reputable PWA-to-Android packaging workflow such as PWABuilder after deploying the app to HTTPS. Review signing, permissions, and package settings before distributing it. Availability and exact workflow can change.

## Data and privacy

- Expense records are stored in this browser's `localStorage` on this device.
- Clearing browser/site data may delete records. Export JSON backups regularly.
- CSV exports contain transaction details; protect exported files.
- Importing JSON replaces the current expense list after validation. Export a backup first.
- This starter app does not sync data between devices.

## Files

- `index.html` — interface and app logic
- `manifest.json` — install metadata
- `sw.js` — offline app-shell cache
- `icon.svg` — app icon
