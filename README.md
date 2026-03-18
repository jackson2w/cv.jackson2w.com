# cv.jackson2w.com

Personal résumé site for Willie Jackson — Learning, Equity & Organizational Growth Leader.

**Live:** [cv.jackson2w.com](https://cv.jackson2w.com)

## Stack

- Single-file semantic HTML5 (`index.html`) — no build step, no dependencies
- Golden Ratio Typography system (18px base, φ = 1.618 line-height, 660px content column)
- Two-font pairing: Lora (headings) + Inter (body) via Google Fonts
- Mobile-responsive at 720px and 480px breakpoints with a print stylesheet
- OG/Twitter card image (`og-image.png`, 1200×630)
- Deployed automatically via Cloudflare Pages on every push to `main`
- Email obfuscation via Cloudflare Scrape Shield

## Deploy

Pushes to `main` trigger an automatic Cloudflare Pages deployment. No build command needed — the output directory is `/`.

See [`DEPLOY.md`](DEPLOY.md) for the initial setup steps.
