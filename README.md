# Kids Games

School holiday experiments with Claude, HTML, and JavaScript for the kids.

## Games

- [Chicken Parkour](parkour.html) — endless runner; tap/click to jump

## Host on Cloudflare (Wrangler)

This is a **static site** (plain HTML/JS). Wrangler needs an assets directory and an `index.html` so it can detect what to upload. Without that you get:

```text
Could not detect a directory containing static files (e.g. html, css and js) for the project
```

This repo already includes `wrangler.jsonc` (assets = project root) and `index.html`.

### Deploy from your machine

1. Install / log in once:

```bash
npm i -g wrangler
npx wrangler login
```

2. Deploy:

```bash
npx wrangler deploy
```

That uses `wrangler.jsonc` and uploads the HTML files from this folder.

### Deploy via Cloudflare dashboard (Git)

1. Workers & Pages → Create → connect the `kids-games` GitHub repo.
2. Leave **build command** empty (nothing to compile).
3. Rely on `wrangler.jsonc` in the repo (do not point at a missing `dist/` folder).
4. Push to `main`; Cloudflare runs `wrangler deploy` and publishes the static assets.

### Local preview

```bash
npx wrangler dev
```

Then open the URL Wrangler prints (usually `http://127.0.0.1:8787`).
