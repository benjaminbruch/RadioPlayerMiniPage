# Radio Player Mini — Website

Marketing and support site for [Radio Player Mini](https://github.com/benjaminbruch/RadioPlayer), a macOS menu-bar internet radio player. Plain static HTML/CSS, no build step, served via GitHub Pages.

## Structure

- `index.html` — marketing landing page (German, default)
- `support.html` — FAQ / support
- `privacy.html` — Datenschutzerklärung (**draft**, needs lawyer review before going live)
- `impressum.html` — Impressum (**draft with placeholder personal data** — fill in real details before going live)
- `en/` — English translations of all four pages above, same filenames
- `assets/` — screenshots and app icon (shared across languages)
- `css/style.css` — shared stylesheet (shared across languages)

## Localization

No build step: each language is a plain directory of HTML files that duplicate the
German ones at root. German stays the default at `/`; English lives under `/en/`.

To add another language (e.g. Spanish):

1. Copy the four `en/*.html` files into a new `es/` directory and translate their content.
2. In every page (all languages), add the new language to `.lang-switch` — link to
   `../es/<page>.html` from root/other-language pages, `es/<page>.html` from root, etc.
   Keep the same filenames and the same anchor IDs (`#funktionen`, `#privacy`) across
   languages so cross-links and the switcher stay simple.
3. Add matching `hreflang` `<link rel="alternate">` tags in `<head>` on every version of
   that page.
4. For `privacy.html`/`impressum.html`, keep the German version as the legally
   authoritative one and say so in the translation's draft banner (already done for `en/`).

## Before going live

- [ ] Fill in real contact email (currently `support@replace-me.example` in `support.html`, `privacy.html`, `impressum.html`, and their `en/` counterparts)
- [ ] Fill in real name/address in `impressum.html` and `en/impressum.html` (marked with `[placeholders]`)
- [ ] Have `privacy.html` and `impressum.html` (German — the legally authoritative version) reviewed by a lawyer
- [ ] Swap the "Demnächst im Mac App Store" / "Coming soon" button for a real App Store link once the app is live (`index.html` and `en/index.html`)
- [ ] Enable GitHub Pages in repo settings (Settings → Pages → Deploy from branch → `main` / root)

## Local preview

Just open `index.html` in a browser — no server or build step needed.
