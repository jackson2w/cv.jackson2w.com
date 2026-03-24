# cv.jackson2w.com

Personal résumé site for Willie Jackson — Senior HR & Talent Development Leader.

**Live:** [cv.jackson2w.com](https://cv.jackson2w.com)

## Stack

- Single-file semantic HTML5 (`index.html`) — no build step, no dependencies
- Golden Ratio Typography system (18px base, φ = 1.618 line-height, 660px content column)
- Lora self-hosted as subsetted woff2 files (Latin range, ~18 KB each) with `font-display: swap`
- Body copy uses the system UI font stack — zero network cost
- Mobile-responsive at 720px and 480px breakpoints with a print stylesheet
- OG/Twitter card image (`og-image.png`, 1200×630)
- Deployed automatically via Cloudflare Pages on every push to `main`
- Email obfuscation via Cloudflare Scrape Shield

## Performance

No external font requests. The previous Google Fonts dependency (fonts.googleapis.com → fonts.gstatic.com) caused a render-blocking chain worth ~1,930ms on cold load. Fonts are now served from the same Cloudflare edge node as the HTML, preloaded in parallel, and swapped in without blocking paint.

## Deploy

Pushes to `main` trigger an automatic Cloudflare Pages deployment. No build command needed — the output directory is `/`.

See [`DEPLOY.md`](DEPLOY.md) for the initial setup steps.
