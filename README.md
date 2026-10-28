<h1 align="center">TNT24 for Jellyfin</h1>

<p align="center">
  All my Jellyfin plugins in one plugin repository.<br>
  Add one URL, and every plugin shows up in your catalog and keeps itself up to date.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/plugins-5-00a4dc" alt="5 plugins">
  <img src="https://img.shields.io/badge/Jellyfin-12.x%20%7C%2010.11.x-00a4dc" alt="Jellyfin 12.x and 10.11.x">
  <img src="https://img.shields.io/badge/notifications-Discord-5865f2" alt="Discord">
</p>

---

## Add the repository

1. In Jellyfin, go to **Dashboard → Plugins → Repositories** (on 10.11: **Dashboard → Plugins → Catalog → ⚙**) and click **+**.
2. Name it `TNT24` and paste this URL:
   ```
   https://raw.githubusercontent.com/TNT24/tnt24-jellyfin/main/manifest.json
   ```
3. Open the **Catalog**, install the plugins you want, and restart Jellyfin.

Jellyfin installs the right build for your server (12.x or 10.11.x) by itself, and its **Update Plugins** task installs new releases automatically.

> Added a plugin's own repository URL before? Remove it, so the plugin doesn't show up twice in the catalog. This repository lists the same releases.

## The plugins

| | Plugin | In short | Jellyfin |
|---|---|---|---|
| <img src="https://raw.githubusercontent.com/TNT24/jellyfin-completionist/main/assets/logo.png" width="120" alt=""> | [**Completionist**](#completionist) | Finds what's missing from your TV shows and film collections | 12.x, 10.11.x |
| <img src="https://raw.githubusercontent.com/TNT24/jellyfin-forced-subtitles/main/assets/logo.png" width="120" alt=""> | [**Forced Subtitles**](#forced-subtitles) | Fills in missing forced and foreign-language subtitles | 12.x, 10.11.x |
| <img src="https://raw.githubusercontent.com/TNT24/jellyfin-plugin-franchise-collections/main/images/logo.png" width="120" alt=""> | [**Franchise Collections**](#franchise-collections) | Makes and maintains movie franchise collections | 12.x, 10.11.x |
| <img src="https://raw.githubusercontent.com/TNT24/jellyfin-seasonal-picks/main/docs/logo.png" width="120" alt=""> | [**Seasonal Picks**](#seasonal-picks) | Movie picks from your watch history and the time of year | 12.x, 10.11.x |
| <img src="https://raw.githubusercontent.com/TNT24/JellyfinThemeBuilder/main/assets/thumb.jpg" width="120" alt=""> | [**Theme Builder**](#theme-builder) | Restyle Jellyfin without writing CSS | 12.1+ |

---

### Completionist

Finds the TV seasons and episodes that have aired, and the films from your collections that have been released, but aren't in your library.

- **TV shows** are compared with an episode guide (TVmaze, or TMDb with a key). Missing whole seasons, single episodes and new episodes that haven't arrived are all listed. Shows no guide knows are checked for gaps in your own numbering.
- **Film collections** list the released films you don't own from each franchise you've started. Needs a free TMDb API key.
- **Its own page in the dashboard** with search, sorting, NEW tags and Ignore buttons.
- **Discord** hears only about *new* gaps, not the same ones every day, with an optional "caught up" message when you fill one.
- Runs daily, after library scans, or with **Check now**.

[Read more →](https://github.com/TNT24/jellyfin-completionist)

### Forced Subtitles

You're watching an English film and a character suddenly speaks Russian. On the disc those lines come with a **forced subtitle**, which rips often lose. This plugin finds what each video is missing and fetches exactly that from OpenSubtitles.com.

- **English audio, no forced subtitle:** downloads a forced subtitle (foreign lines only), if one exists. It never falls back to a full subtitle you didn't ask for.
- **Foreign audio, no subtitle in your language:** downloads a full subtitle (can be turned off).
- **Checks locally first**, so videos that are already covered never touch the API. Ranks exact file-hash matches first and skips machine translations.
- **Handles the daily download limit:** pauses when it runs out and resumes by itself when it renews.
- **Discord** gets a list of what each run downloaded, and a warning if the login stops working.
- Needs a free OpenSubtitles.com account.

[Read more →](https://github.com/TNT24/jellyfin-forced-subtitles)

### Franchise Collections

Creates and maintains collections like *The Matrix Collection* or *Shrek Collection*, using the franchise data Jellyfin's TMDb metadata already stores on each movie.

- A collection is made once you own at least *N* films of a franchise (default 2), with its TMDb poster and overview.
- **Reuses your existing collections** instead of making duplicates, and never removes movies you added by hand.
- Updates a couple of minutes after movies are added, daily, or with **Sync now**.
- Optional generated posters made from the movies' own posters, and a choice of order (release date, name or date added).
- **Locked collections** are left exactly as they are. Pick which libraries to use.
- **Sync and override** makes every collection match TMDb exactly, once.
- **Discord** gets a summary of each sync that creates, fills or deletes collections.

[Read more →](https://github.com/TNT24/jellyfin-plugin-franchise-collections)

### Seasonal Picks

Jellyfin's home screen never says "it's October, how about a horror film you haven't seen in two years?" Seasonal Picks does, on every app, **TV apps included**.

- **A Suggested playlist per user**, refreshed daily, with the reason for each pick. A pick is swapped out as soon as it's watched.
- **Follows the calendar:** Halloween, Christmas, Easter, Valentine's, New Year and special days like Star Wars Day and Chinese New Year. Each season gets its own playlist while it's on, and holiday films stay hidden the rest of the year.
- **Knows what you've seen:** recent watches are left out, and long-forgotten favourites come back as rediscoveries. Understands collections, so it suggests the next film in a series you've started.
- **Seasonal covers** for the playlists, and an optional **Suggested library** folder that shows up as a home row on TVs.
- A **home row and Suggested screen** in the web client, with reroll, "not now" and "never" (needs File Transformation).
- **Discord** announces each season when it starts, and can post one user's picks every day.

[Read more →](https://github.com/TNT24/jellyfin-seasonal-picks)

### Theme Builder

A **Theme Editor** with a live preview, right in the web client. Change colours, cards, the top bar, details pages, the player and more, then save the theme for every user.

- **Lots to change:** accent and background colours (including true OLED black), poster size and corners, badges, details page banners, player colours, the login page, and an optional per-user theme.
- **Presets** to start from, a search that understands everyday words, and a crosshair that finds the option for anything you click.
- **Safe to experiment:** undo and redo, close without saving, go back to the previous save, and export or import a theme as a code.
- **Reaches the TV apps too:** the theme is copied into the server's Custom CSS, which Samsung and LG apps read.
- Needs Jellyfin 12.1 and the [File Transformation](https://github.com/IAmParadox27/jellyfin-plugin-file-transformation) plugin.

[Read more →](https://github.com/TNT24/JellyfinThemeBuilder)

---

## Discord notifications

Completionist, Forced Subtitles, Franchise Collections and Seasonal Picks can post to a Discord channel. They all set up the same way:

1. In Discord, open the channel's settings → **Integrations** → **Webhooks** → **New Webhook** → **Copy Webhook URL**.
2. Paste it into the plugin's **Discord** section and press **Send test message**.
3. Optionally add your server's public address, so messages link to the item in Jellyfin and show its poster.

Messages never ping anyone, and nothing is sent until you add a webhook.

## Problems and ideas

Open an issue on the plugin's own repository (linked above).

## How this repository works

`manifest.json` is built by a GitHub Action from each plugin's own manifest (the list is in `sources.txt`). It runs every hour, so a new release shows up here within an hour of being published. To update straight away, run **Actions → Update manifest → Run workflow**. Don't edit `manifest.json` by hand; the next run overwrites it.
