# Meridian Studio — Website

Static marketing site for Meridian Studio: custom websites, hands-free SEO and
ongoing support, sold with free setup and the first 3 months free.

No build step, no dependencies. Plain HTML and CSS — open `index.html` and it works.

## Pages

| File | Description |
| --- | --- |
| `index.html` | Home — hero, services, work, process, testimonials, about, contact form |
| `pricing.html` | Pricing — three plans (Starter / Pro / Elite), guarantee strip, CTA |

## Structure

```
.
├── index.html       Home page
├── pricing.html     Pricing page
├── site.css         Design tokens, base reset, buttons, header, footer (both pages)
├── home.css         Home-page sections
├── pricing.css      Pricing-page sections
├── site.js          Mobile nav toggle
└── logo.png         "MS" monogram, 400×400
```

`site.css` is shared by every page and holds the design system. Page-specific
styles live in their own file, loaded after it.

All files sit at the repo root — flat, so the paths work unchanged on Netlify,
GitHub Pages, or any static host.

## Design system

All colours, fonts, shadows and spacing come from CSS custom properties declared
on `:root` in `site.css`. Change a token there and it updates
everywhere — don't hardcode values in the page stylesheets.

- **Palette** — navy `#0a1628`–`#2c5490`, steel blues, warm gold accent `#f4b93e`
- **Display type** — Fraunces (headings)
- **Body type** — Inter
- **Container** — `1180px` max width, `24px` gutters
- **Breakpoints** — `1024px`, `880px` (nav collapses), `640px`

Fonts load from Google Fonts; everything else is local.

## Running locally

Any static server works. With Python:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploying

This repo is connected to **Netlify**, which redeploys on every push to `main`.
There is no build step: publish directory is the repo root, build command empty.

For GitHub Pages instead, go to **Settings → Pages** and set _Source_ to
**Deploy from a branch**, branch `main`, folder `/ (root)`.

## Notes

- The contact form on `index.html` posts to `#` — wire it to a form handler
  (Formspree, Netlify Forms, or your own endpoint) before launch.
- Stats, testimonials and case studies on the home page are placeholder content.
- `logo.png` is 236 KB; worth compressing if page weight matters.
