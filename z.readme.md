# Harmony Myofunctional Therapy - Website

Rebuild of harmonymyotherapy.com (originally a Wix site with layout/overlap issues).

## Client
- **Owner:** Kristin Weaver (RDH, COM, IBCLC, Cert. BBM)
- **Referral:** via Jamie (sister-in-law), office manager at Harmony
- **Phone:** 780-238-2335 (office)
- **Email:** reception@harmonymyotherapy.com
- **Arrangement:** Initial rebuild is pro bono. Significant future work may be billable.

## The Site
- Single-page responsive static site (HTML/CSS, vanilla JS)
- Sections: Hero, Services, Speech & Language, How It Works (goals + timeline), Team, Gallery, Locations, Contact
- Fonts: Playfair Display + Inter. Palette: soft green/tan healthcare aesthetic.
- Images scraped from the original Wix site (team photos, logo, gallery) via Puppeteer
- Favicon, scroll animations, Facebook/Instagram links, mobile nav

## Deployment Pipeline (local > UAT > prod)

**Why:** Netlify's new Free plan has a 300 credit/month cap. Each production deploy costs ~15 credits. To avoid burning credits during development, deploys are controlled manually.

1. **Local (dev):** Edit files, preview by opening `index.html` in a browser. Zero cost.
2. **UAT (GitHub Pages):** Push to GitHub -> auto-deploys to https://ackoinos.github.io/harmony-myotherapy/ -- free, unlimited. This is the client review link.
3. **Prod (Netlify):** https://nimble-kheer-85f421.netlify.app (becomes harmonymyotherapy.com once domain is pointed). Netlify is set to "Stopped builds" -- deploys ONLY via manual publish when changes are approved.

## Repo
- GitHub: https://github.com/ackoinos/harmony-myotherapy (public -- required for free GitHub Pages)
- Local: `projects/koinos/harmony-myotherapy/`

## Outstanding
- Waiting on Wix login from Kristin (after Monday) to point domain to Netlify
- Confirm phone/email are the right public-facing contacts
- Any content/photo changes Kristin requests
