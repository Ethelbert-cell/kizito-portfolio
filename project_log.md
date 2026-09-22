# Kizito Cosmos Portfolio — Project Log

---

### [2026-09-22 20:33]
**Task:** > Add developer credit footer with link; fix email card to open mail app with pre-filled subject/body; add Instagram link; center all contact card text.

**Changes:**
* `index.html` (CSS): Added `text-align:center` to `.ccard` to centre all contact card text (WhatsApp, Email, Instagram).
* `index.html` (CSS): Added `footer a` styles — gold colour, no underline, hover opacity transition — for the developer credit link.
* `index.html` (Contact): Updated email `mailto` href with `?subject=Project%20Enquiry&body=...` so clicking opens the mail app with a pre-filled subject and professional body.
* `index.html` (Contact): Updated Instagram card `href` from dead `#` to `https://www.instagram.com/kizito_official1...`; display value updated to `@kizito_official1`.
* `index.html` (Footer): Added "Designed & developed by chimelue.ethelbert" hyperlink pointing to `https://ice-portfolio-beta.vercel.app/` below the main portfolio credit line.

**Logic/Math:** `mailto:` URI uses percent-encoded newlines (`%0A`) and special characters for a cross-client pre-filled body (Gmail, Apple Mail, Outlook).

**Testing:** Manual verification — all three cards centred; email opens mail app with subject + body; Instagram links to correct profile; footer credit link opens in a new tab.

**Phase Progress:** Portfolio site — Contact section & footer polish.

---

### [2026-09-22 19:15]
**Task:** > Integrate real flyer images (flyer1–7) into the graphic design gallery section; remove dummy placeholder images; add "Show All" modal lightbox.

**Changes:**
* `index.html`: Replaced all four CSS-only dummy `.flyer` divs (2 empty black divs, 2 CSS gradient placeholders `.f3`/`.f4`) with real `<img>` elements pointing to `asset/flyer1.jpeg` through `asset/flyer4.jpeg`.
* `index.html`: Removed all dummy CSS classes (`.f1`, `.f2`, `.f3`, `.f4`, `.ftag`, `.ftitle`, `.fmeta`) and replaced `.flyer` styles to accommodate real images with `object-fit:cover` and a subtle hover zoom.
* `index.html`: Added a centred "Show All" button (`.btn-showall`) below the gallery grid, styled with the portfolio's existing gold (`--gold`) accent colour.
* `index.html`: Added a full-screen modal overlay (`#designModal`) containing a 3-column responsive grid displaying all 7 flyers (`flyer1–flyer7.jpeg`).
* `index.html`: Added inline `<script>` with `openModal()` / `closeModal()` functions — scroll-lock (`overflow:hidden`), overlay-click-to-close, and Escape-key-to-close behaviours included.
* No other sections (Hero, About, Video, Services, Work, Contact, Footer) were modified.

**Logic/Math:** No XP or gamification logic involved in this task.

**Testing:** Manual verification — all four gallery images reference valid files in `asset/`; all seven modal images reference valid files in `asset/`; no broken `src` attributes; no references to removed dummy PNGs remain in `index.html`.

**Phase Progress:** Portfolio site — Graphic Design Gallery integration (one-off asset task).

---

### [2026-09-22 19:39]
**Task:** > Integrate video1.mp4 and video2.mp4 from the asset folder into the Videography section of the portfolio.

**Changes:**
* `index.html` (CSS): Added `.vcard video` rule — `display:block; width:100%; aspect-ratio:16/9; object-fit:cover; background:#000;` — so native video elements inherit the existing card layout correctly.
* `index.html` (HTML): Added two new `.vcard` divs inside the existing `#video` `.grid2`, each containing a `<video>` element with `controls`, `muted`, `preload="metadata"`, and a `.vbody` label row (Clip 01 / Clip 02) — matching the existing card structure exactly.
* No autoplay, no sound-on-load. `muted` is set for silent ambient behaviour if user interacts.
* Existing YouTube link cards left completely untouched.
* No other sections modified.

**Logic/Math:** No XP or gamification logic involved.

**Testing:** Manual verification — both `asset/video1.mp4` and `asset/video2.mp4` confirmed present; `src` paths correct; `preload="metadata"` prevents eager full-file download; `aspect-ratio:16/9` keeps correct proportions at all viewport widths; grid collapses to 1-col on ≤640 px via existing `@media` rule.

**Phase Progress:** Portfolio site — Videography section local video integration.

---

### [2026-09-22 19:47]
**Task:** > Fix portrait video fullscreen orientation (videos were displaying horizontal when fullscreened); update YouTube links to correct URLs.

**Changes:**
* `index.html` (CSS): Changed `.vcard video` from `aspect-ratio:16/9; object-fit:cover` → `aspect-ratio:9/16; object-fit:contain`. This renders the portrait frame correctly in-card and tells the browser the natural orientation, so fullscreen uses the video's true vertical dimensions with black side bars instead of forcing landscape.
* `index.html` (CSS): Added `.grid2-portrait` grid class (max-width:480px, centred, 2-col → 1-col on ≤520px) to house portrait clips in a dedicated, proportionate row.
* `index.html` (HTML): Separated YouTube cards (landscape `.grid2`) from local portrait clips (`.grid2-portrait`) into two distinct rows.
* `index.html` (HTML): Updated YouTube href 1: `9SeXYMj9he4` → `9LF9-ISSw2I?si=60jHMeMqoQbZiL84`.
* `index.html` (HTML): Updated YouTube href 2: `EF3hKsgTNBs` → `EznPCHnx5CQ?si=-L-MCDIwllkQw-NW`.

**Logic/Math:** No XP or gamification logic involved. `object-fit:contain` preserves the video's natural pixel aspect ratio in both embedded and fullscreen contexts.

**Testing:** Manual verification — both links point to correct YouTube URLs; portrait aspect ratio applied correctly; responsive breakpoints set for both grid rows.

**Phase Progress:** Portfolio site — Portrait video orientation fix + YouTube link update.

---

### [2026-09-22 19:59]
**Task:** > Change the overall colour theme from purple/indigo to a mature brown-and-gold scheme inspired by the profile photo.

**Changes:**
* `index.html` (CSS tokens): `--bg` → `#1A1008` (espresso), `--panel` → `#241608` (dark walnut), `--panel-2` → `#2E1C0C` (lighter walnut), `--ink` → `#F2EAD8` (warm cream), `--muted` → `#A8916C` (muted tan), `--gold` → `#C8963C` (amber-gold), `--line` → `rgba(242,234,216,0.10)` (cream dividers).
* `index.html` (CSS nav): nav background rgba updated from purple to espresso `rgba(26,16,8,0.92)`.
* `index.html` (CSS hero glow): radial-gradient updated from yellow-gold to amber `rgba(200,150,60,0.14)`.
* `index.html` (CSS portrait): glow and border rgba updated to amber family; ring opacity softened to 0.50.
* `index.html` (CSS .vthumb): fallback gradient changed from indigo (`#241D57,#2E2170`) to dark walnut (`#2C1A08,#3D2410`).
* `index.html` (CSS scrim): warm espresso scrim `rgba(26,16,8,0.35)` replaces purple scrim.
* `index.html` (CSS modal overlay): updated to `rgba(16,9,3,0.90)`.
* `index.html` (CSS btn-solid/btn-showall hover): text color changed to `#1A1008` (espresso) to maintain legibility on amber background.
* All section borders, cards, skill tags, contact cards, footer — automatically pick up new token values via CSS custom properties.

**Logic/Math:** No XP or gamification logic involved. Palette derived from profile photo background (warm medium brown #7B4A2D family) and clothing (deep maroon), targeting a cinematic, mature feel without appearing generic.

**Testing:** Systematic check — every purple/indigo hard-coded hex and rgba replaced; all CSS custom property consumers (panel, ink, muted, gold, line) verified to cascade correctly.

**Phase Progress:** Portfolio site — Full colour theme overhaul.

---

### [2026-09-22 20:03]
**Task:** > Responsive design audit — ensure no horizontal overflow and correct behaviour at 320px, 375px, 390px, 430px, 768px, 1024px, 1280px, 1440px+.

**Changes:**
* `index.html` (CSS html): Added `overflow-x:hidden` to prevent hero glow bleed causing horizontal scroll.
* `index.html` (CSS body): Added `overflow-x:hidden` as belt-and-braces guard.
* `index.html` (CSS .hero-inner gap): Changed fixed `48px` to `clamp(24px,5vw,48px)` for fluid gap between text and portrait at mid-widths.
* `index.html` (CSS mobile hero): Added `padding:60px 0 48px` at ≤640px and `padding:48px 0 40px` + smaller portrait (140×168) at ≤400px to prevent excessive dead space on small phones.
* `index.html` (CSS section): Added `padding:52px 0` at ≤640px and `padding:40px 0` at ≤400px; reduced `.sechead` bottom margin to 26px on mobile.
* `index.html` (CSS .servicerow): Added ≤640px override to stack h3+p vertically (flex-direction:column) so fixed `flex:0 0 220px` basis cannot overflow narrow viewports.
* `index.html` (CSS .project): Added ≤640px override to stack h3+p vertically (flex-direction:column) so fixed `flex:0 0 260px` basis cannot overflow narrow viewports.
* `index.html` (CSS modal): Added ≤480px tighter overlay padding (20px 12px) and modal-box padding (20px 16px 24px) for comfortable display on small phones.

**Logic/Math:** No XP or gamification logic. All grids (.grid2, .designgrid, .contactgrid, .modal-grid) already had correct ≤640px breakpoints — no changes needed there.

**Testing:** Systematic code review at each target breakpoint: 320px ✓, 375px ✓, 390px ✓, 430px ✓, 768px ✓, 1024px ✓, 1280px ✓, 1440px+ ✓. No fixed-width elements wider than viewport at any size.

**Phase Progress:** Portfolio site — Responsive design audit and hardening.

---

### [2026-09-22 21:02]
**Task:** > Fix the mobile hamburger menu to be a compact floating dropdown instead of a full screen overlay.

**Changes:**
* `index.html`: Modified `.mobile-menu` CSS class to remove `left:0`, `right:0`, and full width settings.
* `index.html`: Adjusted position to `right: 28px` with `top: calc(100% + 8px)`.
* `index.html`: Changed the transition from a `clip-path` sweep to an `opacity` and `transform` (slide down) fade-in.
* `index.html`: Added borders, padding, and gap properties so the menu items appear as distinct rectangular buttons with text inside.
* `index.html`: Styled the hover state of the new menu buttons to maintain the existing gold and amber color theme.

**Logic/Math:** No XP or gamification logic involved.

**Testing:** Manual check of CSS logic shows it prevents horizontal scroll and creates the proper layout.

**Phase Progress:** Portfolio site — Mobile Menu UI enhancement.
