# Hiba × Muzthafa — Wedding E-Invite

> *“The Velvet Seal”* — a single-page, scroll-cinematic wedding invitation in deep oxblood velvet and antique gold.

A self-contained, dependency-free invite (one `index.html` + a handful of assets). Tap the wax seal to open it; an instrumental score fades in, the HM crest cracks apart, and the invitation unfolds section by section.

**Sunday · 19 July 2026 · Nikkah 11:00 AM · FLG Conversation Centre, Changaramkulam.**

---

## ✦ Features

- **Seal-break opening** — the HM crest splits like wax and reveals the invite.
- **Embossed, light-reactive gold names** — letterpress relief; on desktop the highlight follows the cursor.
- **Live countdown** to the Nikkah, **Add to Calendar** (`.ics`), and **tap-to-call**.
- **Custom engraved map** — a gold-on-oxblood map of Changaramkulam, with “Get Directions” → Google Maps and a scannable QR.
- **Send Your Blessings** — one tap opens WhatsApp to the family with a pre-written dua.
- **Ambient atmosphere** — drifting gold dust, candlelight flicker, slow damask parallax.
- Mobile-first, `prefers-reduced-motion` aware, ~0.5 MB initial load (music is deferred until first tap).

## ✦ Structure

```
index.html          # the entire invite (HTML + CSS + JS inline)
assets/
  seal.png          # HM monogram crest (transparent)
  damask.jpg        # oxblood velvet background
  map.jpg           # engraved gold-on-oxblood venue map
  qr.png            # QR to the venue location
  og-card.jpg       # 1200×630 social share card
  score.mp3         # ambient instrumental score
```

## ✦ Run locally

It needs to be served over HTTP (the audio and share card won’t work from a `file://` path):

```bash
# any static server, e.g.
python -m http.server 5510
# then open http://localhost:5510
```

## ✦ Deploy

Static site — works on Vercel, Netlify, Cloudflare Pages, or GitHub Pages with **no build step**.

**Vercel:** import this repo → Framework Preset **“Other”** → deploy. That’s it.

### After deploying — update the share preview
WhatsApp / iMessage need an **absolute** image URL to show a link preview. In `index.html` (`<head>`), replace the two `REPLACE-WITH-YOUR-DOMAIN` placeholders in `og:url` and `og:image` with your live URL, then redeploy.

---

*Map data © OpenStreetMap contributors, © CARTO.*
