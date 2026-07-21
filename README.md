# anti-clockwise-web

Static website for Anti-Clockwise, LLC. Deployed on Cloudflare Pages.

## Structure

- `index.html` — homepage
- `About.html`, `Consulting.html`, `Contact.html`, `Privacy.html`, `Products.html` — site pages
- `support.js` — runtime that powers these pages (templating, hover styles, etc.). This file is **generated from `dc-runtime/src/*.ts`** and should not be edited by hand — rebuild it with `cd dc-runtime && bun run build`.

No build step is required to serve the site itself — it's plain static HTML/JS/CSS.

## Deployment

The site is static-hosted on Cloudflare Pages, deployed straight from this repo's root — no build command or output directory configuration needed.
