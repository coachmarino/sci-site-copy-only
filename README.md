# South Coast Inbound: copy rebuild preview

Static rebuilds of three southcoastinbound.com pages, written to the Local Business Copywriting Bible and using only facts published on the live site.

- `/` (home)
- `/local-seo-services-massachusetts-rhode-island-south-coast-inbound/`
- `/digital-marketing-agency-in-providence/`

## Build
`node build.mjs` writes the static site to `dist/` and a single-file Cloudflare Pages worker to `dist-worker/_worker.js`.

## Preview safety
The preview is kept out of search three ways: `<meta name="robots" content="noindex, nofollow, noarchive">` on every page, an `X-Robots-Tag` header (in `site/_headers` and set by the worker), and `robots.txt` disallowing everything. Canonical tags point at the live URLs. Images are loaded from the live site; consultation links go to the live consultation page.
