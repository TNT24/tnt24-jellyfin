# TNT24 for Jellyfin

One plugin repository for all of my Jellyfin plugins. Add it once and every plugin shows up in the catalog, with updates.

## Add the repository

1. In Jellyfin, go to **Dashboard → Plugins → Repositories** (on 10.11: **Dashboard → Plugins → Catalog → ⚙**) and click **+**.
2. Name it `TNT24` and paste this URL:
   ```
   https://raw.githubusercontent.com/TNT24/tnt24-jellyfin/main/manifest.json
   ```
3. Open the **Catalog** and install what you like. Restart Jellyfin after installing.

If you added any of these plugins' own repository URLs before, you can remove them; this one lists the same releases.

## Plugins

| Plugin | What it does | Jellyfin |
|---|---|---|
| [Completionist](https://github.com/TNT24/jellyfin-completionist) | Finds aired TV seasons and episodes, and released films from your collections, that are missing from your library. Optional Discord notifications. | 12.x, 10.11.x |
| [Forced Subtitles](https://github.com/TNT24/jellyfin-forced-subtitles) | Downloads missing forced and foreign-language subtitles from OpenSubtitles.com. Optional Discord notifications. | 12.x, 10.11.x |
| [Franchise Collections](https://github.com/TNT24/jellyfin-plugin-franchise-collections) | Creates and maintains movie franchise collections from TMDb data. Optional Discord notifications. | 12.x, 10.11.x |
| [Seasonal Picks](https://github.com/TNT24/jellyfin-seasonal-picks) | Picks movies for each user from their watch history and the time of year, as playlists that work on TVs too. Optional Discord posts. | 12.x, 10.11.x |
| [Theme Builder](https://github.com/TNT24/JellyfinThemeBuilder) | A live theme editor for the web client, no CSS needed. | 12.1+ |

## How it works

`manifest.json` is built by a GitHub Action from each plugin's own `manifest.json` (listed in `sources.txt`). It runs every hour, so a new release shows up here within an hour of its plugin manifest being pushed. To update straight away, run **Actions → Update manifest → Run workflow**. Don't edit `manifest.json` by hand; the next run overwrites it.
