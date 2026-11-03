# Anime Shelf

Rate your anime and manga from S to C, note where to watch or read them, and get the cover automatically. Installable web app.

- Covers and suggestions come from the AniList API (https://graphql.anilist.co), with Jikan (https://api.jikan.moe) as a fallback. Covers are linked, not stored.
- Data: Supabase tables `shelf_items`, `shelf_scores` and `shelf_members` (allow-list), protected by row level security. Google sign-in; this app's address must be in the Supabase Auth redirect URLs. To let someone in: `insert into shelf_members (email, name) values ('them@gmail.com', 'Name');`
- Hosting: Cloudflare Workers static assets (`wrangler.jsonc`), deployed automatically on every push to `main`.
- Each release is listed in [CHANGELOG.md](CHANGELOG.md). When shipping, bump `APP_VERSION` in `index.html` and the `CACHE` name in `sw.js`.
