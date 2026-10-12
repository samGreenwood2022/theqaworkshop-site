# The QA Workshop: landing page

Source for [theqaworkshop.co.uk](https://theqaworkshop.co.uk), the landing page for Sam Greenwood's 1-to-1 test automation coaching. It's plain static files with no build step.

| File | What it is |
|---|---|
| `index.html` | The landing page (all styles inline) |
| `privacy.html` | Privacy policy, linked from the footer |
| `og-image.png` | 1200×1200 share image used by the Open Graph / Twitter meta tags |
| `sitemap.xml` | Sitemap listing the two pages |

## Deploying to Cloudflare

The site is served from a Cloudflare Worker with static assets. **Every deploy replaces the whole asset set, so always upload all four files together.** Uploading only `index.html` makes `privacy.html`, `og-image.png` and `sitemap.xml` return 404.

After a deploy, check:

- https://theqaworkshop.co.uk/
- https://theqaworkshop.co.uk/privacy.html
- https://theqaworkshop.co.uk/og-image.png
- https://theqaworkshop.co.uk/sitemap.xml

Optional: Cloudflare can deploy straight from this repo (Workers & Pages, then connect to Git), so a push to `main` publishes all the files automatically.

## Editing

- **Testimonials:** the `quote-grid` block in `index.html`. Each is a `<div class="quote">` with a `<blockquote>` and a `<cite>`.
- **Pricing, FAQ, booking link:** also in `index.html`. The Calendly link is repeated in several buttons, so search for `calendly.com`.
- **Privacy policy:** update the "Last updated" date in `privacy.html` and the `lastmod` dates in `sitemap.xml` when you change it.
- **Share image:** `og-image.png` is a static export. If you change the headline, regenerate the image and keep it at 1200×1200 (the size declared in `index.html`).
