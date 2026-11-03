# Anime Shelf

Rate your anime and manga from S to C, note where to watch or read them, and get the cover automatically. Installable web app.

- Covers and suggestions come from the AniList API (https://graphql.anilist.co), with Jikan (https://api.jikan.moe) as a fallback. Covers are linked, not stored.
- Sync: Supabase (same project and allowed-account list as the Control Room), row `anime-shelf/main` in `control_room_docs`. Needs this app's address added to the Supabase Auth redirect URLs.
- Hosting: Cloudflare Workers static assets (`wrangler.jsonc`), deployed automatically on every push to `main`.
- Each release is listed in [CHANGELOG.md](CHANGELOG.md). When shipping, bump `APP_VERSION` in `index.html` and the `CACHE` name in `sw.js`.
