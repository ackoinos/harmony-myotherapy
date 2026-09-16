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

# 2026-09-09 15:00 - Jen/Jamie site review pending

> Kristin's email (re: new Integrative company) mentioned she's meeting Jen and Jamie to review the Harmony Myotherapy site and give better guidance.

**Actions Taken:**
- Added to Outstanding list in z.readme.md: waiting on guidance from Kristin's review with Jen and Jamie -- likely source of the pending content/photo changes.
- Tracked as MasterToDo KOI-00082 under Koinos.
- Acknowledged in the reply drafted to Kristin (reply lives in the harmony-integrative-poc project since it's primarily about the new company).

# 2026-09-15 - Round 2 tweaks (from Kristin follow-up review)

> Kristin reviewed the first round and asked for: drop the "SLP" abbreviation, shorten default team bios (full on click), bigger therapist photos / lightbox, make the gallery an actual reel, rebuild Q&A to match the services accordion as its own tab, and add a Blog tab. Provided referral/Q&A/blog URLs.

**Actions Taken:**
- Transcribed the full Loom video (had to pull the complete MP4 via Loom's transcoded-url API; the browser-scraped chunk was video-only/no audio). Fixed a cublas cu12/cu13 DLL mismatch in the GPU whisper venv to run faster-whisper.
- Removed "SLP" badge/term from the speech services card
- Team cards: added short one-line intros (shown by default), full bios behind Read Bio, photos enlarged to 210px, click-to-open lightbox
- Gallery converted from manual carousel to a continuous auto-scrolling reel (pauses on hover, click opens lightbox)
- Created `questions-and-info.html`: dedicated page, accordion of all 12 real topics from her Wix Q&A, styled like the FAQ/services section
- Created `blog.html`: dedicated blog listing page with her existing tongue-tie training post; structured for easy additions
- Added Questions & Info + Blog to nav and footer on all pages
- Referral form: hidden Web3Forms static form still in back pocket; live links point to Wix referral for now
- Worked on branch `feature/round2-tweaks`, merged to master with --no-ff

**Still outstanding:**
- Blog is static (Wix blog is dynamic). If Kristin posts often and wants self-service, a small CMS is a future paid option.
- "For Referring Professionals" tab (separate professional referral form) - not yet built
- Harmony Integrative Orofacial Health page - separate future project (she'll send details)
- Wix login still needed to point the domain

# 2026-09-15 - Round 3 tweaks + bug fix + Q&A media

> Follow-up review: Read Bio buttons not expanding; add original Q&A clinical photos/links/videos; speech card was a different color (make it match); Karen Pollock and Erin Larkin headshots sit lower than the others.

**Actions Taken:**
- BUG FIX: hidden lightbox overlay (`position:fixed; inset:0`) was intercepting ALL clicks because `[hidden]` was overridden by `display:flex`. This silently blocked the Read Bio toggles, FAQ accordion, and gallery. Fixed with `.lightbox[hidden] { display:none }`. Diagnosed via headless Puppeteer click test (elementFromPoint returned the lightbox div). Committed straight to master.
- Scraped the original Q&A clinical photos via CDP network interception (Wix lazy-loads per accordion topic; had to click each topic + capture image responses). Re-fetched at larger size, renamed to friendly names in `images/qa/`.
- Added photos to Q&A topics: Mouth Breathing (open mouth posture, enlarged tonsils), Tongue-Tie (tongue-tie, maxillary frenum, release), Anterior Open Bite (open bite, post-therapy result, narrow vs normal arch), Habit Elimination (thumb sucking), Lactation (breastfeeding). Added lightbox to Q&A page.
- Scraped Q&A for videos/links: no real embedded videos (only Wix player JS). Two real reference links added as clickable: Camacho 2015 sleep apnea study (academic.oup.com) and Kristin's Buteyko Clinic International profile.
- Removed the highlighted green background on the Speech & Language services card so it matches the other cards
- Fixed Karen Pollock + Erin Larkin headshot framing (their faces sit lower in the source photos) with `.team-img-lower { object-position: center 35% }`
- Worked on branches `feature/qa-photos` and `feature/round3-tweaks`, merged to master

**Still outstanding:**
- Blog is static (one post); dynamic self-service posting would need a CMS (future paid option)
- "For Referring Professionals" tab - not yet built
- Harmony Integrative Orofacial Health page - separate future project
- Wix login still needed to point the domain

# 2026-09-15 - Q&A media accuracy fix + reply email

> Kristin flagged: Q&A pictures didn't match sections, Mouth Breathing and Sleep Apnea had YouTube videos, and there was a Photo Examples section. Also asked to review the referral form and whether to stay on Wix.

**Actions Taken:**
- Re-scraped Q&A page topic-by-topic (structural DOM capture) to map media accurately. Found the clinical photos all belong to a "Photo Examples" section, not scattered across topics.
- Extracted the two YouTube video IDs by triggering Wix's lazy-loaded video players and capturing embed URLs from network traffic: Mouth Breathing (3h0JgmmLj_Q), Obstructive Sleep Apnea (cxEWHV67JIU).
- Rebuilt Q&A page: added Photo Examples section (6 clinical photos), embedded both videos (youtube-nocookie, responsive 16:9), corrected per-topic images, matched original topic order. Removed images that weren't actually in their sections.
- Confirmed Web3Forms free tier: 250 submissions/month free forever, no card. Verified via their pricing page.
- Drafted reply email to Kristin (`reply-to-kristin-2026-09-15.md`) summarizing all round 2/3 changes and laying out the Wix stay-or-leave decision in non-technical terms, including a plain-language note that the built-in form uses a free email service (same model as Wix, nothing new in data handling).
- Sent Kristin the GitHub Pages preview link (always current) rather than the Netlify one (stopped builds).

**Still outstanding:**
- Kristin to decide: stay on Wix vs move off (activates the hidden Web3Forms referral form + domain switch)
- Wix login needed to point the domain
- "For Referring Professionals" tab, blog CMS, Harmony Integrative Orofacial Health page - future

# 2026-09-15 - Logo hi-res + Kristin feedback round

> Kristin: logo small/blurry at top. Then replied loving the site with 3 points: (1) already paid 3yr Wix so staying on Wix, (2) wants to eventually link Harmony Integrative Orofacial Health (sister company), (3) remove the tongue-tie release photo since they do therapy not the surgery.

**Actions Taken:**
- Re-fetched logo from Wix CDN at 1200x540 (was 191x86) -> `images/logo-full.png`. Sharp now.
- Nav logo 64px full-color on light header; footer logo 64px white-on-dark (brightness(0) invert(1)) restored after a brief misstep with a white background box.
- Tongue-Tie topic: removed only the caption "Tongue-tie release at Harmony" (kept the image). Kristin's note was on the caption, not the photo. Softened "surgical outcome" -> "outcome" (they do therapy, not surgery).
- Drafted reply email `reply-to-kristin-2026-09-15b.md`.

**Decisions locked:**
- Staying on Wix (3yr prepaid) -> referral buttons keep pointing to the Wix form. Hidden Web3Forms form stays as back-pocket only.

**Next session TODO (chat was getting long, continuing fresh):**
- Link "Harmony Integrative Orofacial Health" (sister company) - add to nav as a link to their site or a section/page here. Waiting on Kristin for their URL, logo, and a blurb.
- "For Referring Professionals" tab - still not built.
- Blog CMS - future, only if she wants self-service posting.
- Domain switch NOT happening (staying on Wix), so no DNS/CNAME work needed. Site lives on GitHub Pages preview (ackoinos.github.io/harmony-myotherapy) unless she wants it on the real domain later.
