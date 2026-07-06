# FWMH — product website

Marketing site for **FWMH ("Flow with milk and honey")**, a scripture-aware notebook by
Byteraft Limited. Single self-contained `index.html` (no build step, no dependencies, no
external requests) designed for **GitHub Pages**.

**Live domain:** https://fwmh.byteraft.io

## What's here

| File | Purpose |
|------|---------|
| `index.html` | The whole site — HTML, CSS and JS inline. |
| `assets/app-bible.png` | Real screen capture of the FWMH app (Android). |
| `assets/og.svg` | Social share image (Open Graph / Twitter). |
| `CNAME` | GitHub Pages custom domain (`fwmh.byteraft.io`). |
| `robots.txt`, `sitemap.xml` | SEO. |
| `404.html` | Branded not-found page. |
| `.nojekyll` | Serve files as-is (no Jekyll). |

## Features

- **Trilingual** — English, 繁體中文, 简体中文, matching the app. Language **auto-detects**
  from the browser, switches with the `EN / 繁 / 简` control, persists in `localStorage`, and
  is shareable via `?lang=zh-Hant` / `?lang=zh-Hans`. English is in the HTML for SEO/no-JS;
  Chinese strings live in `window.I18N`, keyed by `data-i18n`.
- **Light / dark** — the app's real amber-on-cream palette, following the OS with a manual toggle.
- **Real pricing** — Free tier + FWMH Plus (Individual **US$11.49/mo**, Student **US$7.59/mo**),
  a Free-vs-Plus feature table, group-devotion streak rewards, and a pricing FAQ.
- **SEO** — canonical + `hreflang`, Open Graph, Twitter, JSON-LD `SoftwareApplication`,
  sitemap and robots.
- **Responsive**, reduced-motion aware, no external fonts/scripts/trackers.

## Updating the app screenshot

`assets/app-bible.png` is a real capture from the Android build. To refresh it, run the app
on the emulator (`../run-fwmh-android.sh`) and:

```sh
adb exec-out screencap -p > assets/app-bible.png
```

Keep it at the device resolution (portrait, ~1080×2400) — the phone frame uses that aspect ratio.

## Deploy on GitHub Pages

1. Push to a GitHub repo; **Settings → Pages →** deploy `main`, root.
2. `CNAME` sets `fwmh.byteraft.io`; add a `CNAME` DNS record for `fwmh` → `<your-user>.github.io`.
   (If you use the default `*.github.io` URL, edit `CNAME` and the absolute URLs in
   `index.html`, `sitemap.xml`, `robots.txt`.)

## Editing copy

Edit the English text in `index.html`, then update the matching `data-i18n` key in
`window.I18N` for `zh-Hant` and `zh-Hans`. Cross-links to the company site point at
`https://www.byteraft.io`.
