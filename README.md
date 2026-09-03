# Canyon Peak Holdings — corporate site

Static marketing and policy site for **Canyon Peak Holdings Inc.** and its subsidiaries,
Canyon Peak Technologies, LLC and Canyon Peak, LLC (which owns FinishAtlas, LLC). Hosted on Cloudflare and served at
<https://www.canyonpeak.co>.

## Pages

| Path | Purpose |
|---|---|
| `index.html` | Home: company structure, products, policy links, contact |
| `privacy.html` | Privacy Policy (Apple App Store, Google Play, and Twilio requirements) |
| `sms-policy.html` | SMS & Email Messaging Policy (Twilio / CTIA / TCPA / CAN-SPAM) |
| `404.html` | Not-found page (Cloudflare Pages serves this automatically) |

Cloudflare Pages serves clean URLs, so `/privacy` and `/sms-policy` resolve to the `.html`
files. Use these URLs in app-store listings and Twilio A2P 10DLC campaign registration:

- Privacy Policy: `https://www.canyonpeak.co/privacy`
- SMS terms: `https://www.canyonpeak.co/sms-policy`

## Structure

```
assets/brand/   Canyon Peak "Contour" brand assets (SVG masters + PNG marks)
assets/css/     site.css — shared stylesheet, brand tokens
assets/js/      site.js — footer year, mobile nav toggle
_headers        Cloudflare security headers + asset caching
robots.txt, sitemap.xml
```

The wordmark lockups are rendered as HTML text (Barlow Condensed via Google Fonts) next to
the inline SVG mark, because an SVG loaded through `<img>` cannot use web fonts. Colour and
type follow `Canyon Peak Brand Assets/04-specs`.

## Editing policies

Both policy pages carry an **Effective / Last updated / Version** block at the top. When you
change substantive wording, bump the date and version and, for material changes, notify users
in the affected product before the change takes effect (see the "Changes" section of each
policy). Keep `sitemap.xml` `lastmod` in step.

## Local preview

```bash
python -m http.server 8787
```

Then open <http://localhost:8787/>. There is no build step.

## Notes

- The CleanCycle laundry venture is on hold and is not shown on the site. Its logo is kept at
  `assets/cleancycle-logo.png`.
- The apex domain `canyonpeak.co` currently has no DNS record; only `www` resolves. Add an
  apex record or redirect in Cloudflare so the canonical URLs work without `www`.
