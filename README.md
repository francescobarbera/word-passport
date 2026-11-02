# Word Passport

A small English-practice website for Italian-speaking learners. Listen to country names and nationalities, then repeat them aloud.

**Website:** https://word-passport.barbera.me

## Features

- 107 entries: Italian country name, English country name, and English nationality.
- A pronunciation button beside each English word.
- Search across all three columns, ignoring accents and case.
- A slower-pronunciation toggle that immediately replays the last word.
- Responsive layout and keyboard-accessible controls.

## Pronunciation

The page uses the browser's Web Speech API, preferring **Daniel (British English)**. If Daniel is unavailable, it automatically selects another British English voice, then the device’s default English voice, then any available English voice. No voice selector is needed. If the browser has not exposed its voice list yet, the page requests British English directly from the speech engine. If a loaded voice list contains no English voices, the page explains how to add one. It does not contain recorded audio or use a paid speech service. Availability varies by operating system and browser, and some voices require an internet connection.

Normal playback requests rate `1`; slow playback requests `0.45`. Actual timing depends on the speech engine.

## Run locally

Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

Then visit http://localhost:8000. No packages, build step, or API keys are required.

## Edit

HTML, CSS, vocabulary, and JavaScript live in `index.html`. The `raw` string contains one vocabulary entry per line, with three fields separated by `|`.

## Deployment

GitHub Pages serves the root of the `main` branch. Pushing to `main` automatically updates the website. `.nojekyll` disables Jekyll processing, and `CNAME` declares the custom domain.

Cloudflare DNS configuration for the `barbera.me` zone:

| Setting | Value |
| --- | --- |
| Type | CNAME |
| Name | word-passport |
| Target | francescobarbera.github.io |
| Proxy status | DNS only |
| TTL | Auto |

In GitHub Settings → Pages, set the custom domain to `word-passport.barbera.me` and enable **Enforce HTTPS** once GitHub has issued the certificate.

## Possible next step

Fill-in-the-blank exercises for practising country names and nationalities.
