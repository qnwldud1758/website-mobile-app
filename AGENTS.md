# AGENTS.md

## Architecture
- Plain static site, no build step. `netlify.toml` publishes `public/`.
- `public/index.html` holds everything: markup, Tailwind config, styles, the tool dataset (`aiTools` array), and the UI logic (filters, sort, bookmarks in localStorage, detail modal, `?tool=<slug>` deep links).
- PWA: `public/manifest.webmanifest`, `public/sw.js` (network-first for pages, cache-first for assets), and icons in `public/icons/`.

## App install flow
- Any element with the class `install-trigger` opens the install modal (`#installModal`). An optional `data-os="android|ios|desktop"` picks the tab.
- `beforeinstallprompt` is captured so supported browsers get a one-click install button. iOS shows manual Safari steps.
- `/install` is rewritten to `index.html` (see `netlify.toml`). It and `?install=1&os=...` open the modal on load.
- `public/icons/install-qr.svg` encodes `https://website-mobile-app.netlify.app/?install=1`. Regenerate it if the domain changes (e.g. with the `qrcode` npm package).

## Conventions
- UI copy is in Korean. Reuse the existing Tailwind utility style and the global `showToast()` helper.
- When you change cached assets, bump `CACHE` in `sw.js` so clients pick up the new version.
