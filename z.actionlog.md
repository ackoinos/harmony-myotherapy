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
