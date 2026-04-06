# nv:context landing page

The landing page for [nv:context](https://github.com/johnnichev/nv-context) — context engineering for engineers who ship.

Built in one afternoon using [nv:design](https://github.com/johnnichev/nv-design), the Vibe Design methodology that uses source code as the design reference instead of prompts or screenshots.

## Stack

- Pure HTML / CSS / JavaScript — no framework, no build step
- Google Fonts CDN: Inter, Instrument Serif, JetBrains Mono
- Single self-contained `index.html` (~92KB)
- Hosted on Vercel

## Local development

```bash
python3 -m http.server 4774
# open http://localhost:4774/
```

## How it was built

1. **Downloaded references**: Linear, Resend, Railway via [Asimov Site Downloader](https://sd.asimov.academy)
2. **Extracted design systems**: Capability 1 of nv:design — `linear-ds.html` + `resend-ds.html`
3. **Recombined**: Capability 2 — merged Linear's motion vocabulary with Resend's developer-tool aesthetic into `hybrid-ds.html`
4. **Built section-by-section**: Capability 3 — hero, then proof, then problem, then laws, then file tree, leverage, research, install CTA

The recombined design system lives in `/design-systems/hybrid-ds.html` and is the source of truth for every CSS variable and component class on the page.

## License

MIT
