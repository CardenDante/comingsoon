# TerraVista Safaris — Coming Soon

A single static holding page for the main domain while the full site is being
finished.

No build step, no dependencies — `index.html` plus five assets. Open the file
directly, or serve the folder:

```bash
python3 -m http.server 3300    # http://localhost:3300
```

## Deploying

Point the host at this folder as a **static site** — there is nothing to build.

| Host | Setting |
| --- | --- |
| Vercel / Netlify | Framework preset: **Other**. Build command: *(empty)*. Output directory: `.` |
| cPanel / shared hosting | Upload the contents of this folder to `public_html` |
| S3 / Cloudflare Pages | Upload as-is; index document `index.html` |

When the real site is ready, repoint the domain at the Next.js app and this
folder can be dropped.

## Design

Deliberately the same brand as the main site, with the tokens lifted directly
from its `globals.css` rather than re-invented:

- **Palette** — oxblood ground `#2a1010`, burnt-orange accent `#db7532`
- **Type** — Kristi script eyebrow, Oswald condensed uppercase heading,
  Montserrat body (the same four-font stack as the site, via Google Fonts)
- **Motifs** — the centred diamond rule, the leopard watermark flattened to
  white, and the warm radial glow used on the site's closing band

The CSS is hand-written rather than Tailwind because this has to stay a single
portable file.

## Notes

- `robots` is `noindex, follow` — a holding page should not be what search
  engines index as the site. Nothing to undo later; this folder goes away.
- The buttons are `tel:`, `mailto:` and a `wa.me` link, so there is **no
  backend and no form** to maintain. Enquiries keep arriving on the channels
  the team already watches.
- Text contrast over the photograph was measured, not eyeballed — heading
  9.1:1, body 6.5:1, tagline 5.2:1, contact row 7.2:1, all clearing WCAG AA.
- Assets are copies of the main site's (`logo-white.png`, `leop-1.png`,
  `desktop-poster.webp`, icons). If the logo changes, recopy them here.
- **Icons** are the supplied `public/logo-white-512.png`, used as-is.
  `icon.png` is a byte-for-byte copy; `apple-icon.png` and `favicon.ico`
  (16/32/48/64) are the same artwork resized only to fit those formats —
  nothing cropped, no background added. Note the wordmark is white, so on a
  light browser tab only the sun and elephant read; the text shows on dark.
