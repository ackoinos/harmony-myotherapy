# 2026-08-27 15:30 - User Request

> New website build for Harmony Myofunctional Therapy (harmonymyotherapy.com). Owner's complaint: overlapping elements, poor placement, current web developer unresponsive and wants to charge more to fix issues. Rebuild into something better.

**Actions Taken:**
- Fetched all content from the existing Wix site (homepage + about/team page)
- Created project folder at `projects/koinos/harmony-myotherapy/`
- Built a complete single-page responsive site (`index.html` + `styles.css`)
- Sections: Hero, Services (8 cards), Speech & Language, How It Works (4 goals + timeline), Team (7 members), Locations, Contact CTA, Footer
- Clean healthcare aesthetic (green/tan palette, Playfair Display + Inter), mobile-first, no overlaps

# 2026-08-27 15:45 - User Request

> Add images to the site. Can we use ones from the original? (Answer: Wix CDN makes direct extraction impossible, using Unsplash placeholders instead)

**Actions Taken:**
- Added full-bleed hero background image with dark overlay for text contrast
- Added section break image between services and speech/language
- Added photo alongside the speech & language section (split layout with image on left)
- Replaced all team initial-circle placeholders with Unsplash headshot photos
- Updated CSS for image handling: hero overlay, object-fit cover, responsive image sizing, team photo circles
- Updated hero text/button colors to work on dark background

# 2026-08-27 16:30 - Deployment Pipeline Setup

> Discussed Netlify credit consumption (300 credit/month cap on new Free plan). Set up a local > UAT > prod pipeline to control credit usage.

**Actions Taken:**
- Diagnosed Netlify credit drain: 195 of 196 credits consumed by 13 production deploys (~15 credits each). Traffic/bandwidth negligible.
- Set Netlify to "Stopped builds" so GitHub pushes no longer trigger auto-deploys (no credit burn during dev)
- Made GitHub repo public and enabled GitHub Pages (private repos need paid plan for Pages)
- Added real contact info to site: phone 780-238-2335, email reception@harmonymyotherapy.com
- Added Facebook and Instagram social links to footer
- Fixed favicon (cropped icon mark from logo instead of squishing full wordmark)

**Pipeline established:**
- Local (dev): edit + preview by opening index.html
- GitHub Pages (UAT): https://ackoinos.github.io/harmony-myotherapy/ -- Kristin's review link, free/unlimited
- Netlify (prod): live site at nimble-kheer-85f421.netlify.app, manual publish only

**Client status:** Kristin approved the design. Old Wix site being finished by prior developer on Monday. Waiting on Wix login to point domain (harmonymyotherapy.com). Work is pro bono for initial build.
