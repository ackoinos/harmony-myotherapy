# Change Request - Loom Video from Kristin & Jen (2026-09-15)

Source: https://www.loom.com/share/089cc98db34b43dea6d105a1039493d5 (~5 min, Kristin + Jen)

Overall: They love the design and appearance. These are tweaks, not a redo.

## Navigation
1. **Remove "Speech & Language" as a top nav item.** Fold it under Services instead. Reason: Kristin doesn't want to highlight it separately, feels it takes away from the other practitioners.

## Hero / Book a Consultation
2. **"Book a Consultation" button** should link to her **self-referral form** (exists on her old Wix site). Need that form URL/setup.

## Services section
3. **Add an "SLP" / Speech & Language box** within the Services grid. Note in it that speech & language is **"select locations only."**
4. Remove the standalone speech & language highlight treatment (tie-in to #1).

## Team section
5. **Make team cards/photos bigger** so you can see the therapist better.
6. Show **name + credentials** by default; **bio drops down on hover/click** (a "read bio" expander).

## Gallery
7. Convert gallery to a **reel/carousel format** (scroll through) instead of the static grid, easier to look at.
8. Some pictures are off-center (she thinks the reel format will self-correct this).

## Locations
9. **Add Sherwood Park** as a location.
10. Each location, when clicked, should link to the **referral form submission** (from old site).

## Contact / "Ready to Get Started"
11. **Remove "speech and language services"** mention from this section. Keep it generalized to myofunctional therapy.

## New sections / tabs
12. **Q&A section** - use the same expand/collapse (accordion) format as the "How It Works" click-to-expand. Content from the Q&A on her old site.
13. **Blog** - she has a blog on the old site, wants to keep it running (likely a new tab/page).
14. **"For Referring Professionals" tab** - an online referral for professionals. Separate referral form (exists on old site).

## Dependencies (need from Kristin)
- Self-referral form (URL or the form itself from old Wix site) - used in multiple places (#2, #10)
- "For Referring Professionals" referral form (#14)
- Q&A content (#12)
- Blog content / how it's currently hosted (#13)
- Sherwood Park location details (#9)

## Notes
- Separate future project mentioned: "Harmony Integrative Oral and Facial Health" page - she'll send details later. Not part of this change set.

## Follow-up info from Kristin (2026-09-15, later)

### Referral form
- Wix referral form: https://www.harmonymyotherapy.com/referral
- **Decision needed:** Wix form won't work if we leave Wix. Our GitHub site is static.
- **Recommended solution:** Rebuild the form as static HTML wired to a form-handling service (Web3Forms or Formspree, free tier). Submissions email to reception@harmonymyotherapy.com. No Wix, no backend to run.
- Referral form is a CLINICAL CONCERN CHECKLIST. Fields captured from Wix:
  - Restrictive Sublingual Frenulum, Restrictive Maxillary Labial Frenulum, Restrictive Mandibular Frenulum, Restrictive Buccal Frenulum
  - Tongue-Thrust, Anterior Open Bite, Posterior Open Bite
  - Mouth Breathing, Dysfunctional Breathing
  - Thumbsucking/Finger Sucking, Other Negative Oral Habit
  - Concerns for Craniofacial Growth and Development, Orofacial Pain
  - Improper Tongue Rest Posture, Sleep/Airway, Speech
- Simple contact form fields (from footer): First name, Last name, Email, Phone, Location, Message

### Q&A page
- https://www.harmonymyotherapy.com/questions-and-info
- Content is more educational sections than strict Q&A (OMD causes, tongue-tie explainer, thumb sucking program, Buteyko, lactation/IBCLC). Need to shape into accordion or a hybrid info+FAQ layout.

### Full staff bios
- Scraped full "Show More" bios for all 7 team members. Current cards use shortened versions. Replace with full bios behind the Read Bio toggle.

### Confirmed nav on real site
- Services, Questions and Info, About, Referral, Harmony Integrative Orofacial Health, Blog, Contact
- Confirms: Blog exists (keep running), separate "Harmony Integrative Orofacial Health" page (future project)

### Confirmed locations
- Calgary, Edmonton, Sherwood Park, Leduc, Beaumont, Grande Prairie
