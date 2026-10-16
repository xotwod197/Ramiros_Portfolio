# CLAUDE.md — Portfolio site project notes

**Read this first.** This file is the hand-off between work sessions on different machines and
different Claude accounts. It holds what the site is, the content rules Ramiro has set (these
matter more than the code), and a dated log of every change. **At the end of any session that
changes the site, add an entry to the Changelog below and commit it with the change.** Keep it
short and factual.

This repo is public and the site is live — nothing sensitive goes in this file, the pages, or the
screenshots (see Content rules).

---

## What the site is

Ramiro Herrera's personal portfolio. Static site, GitHub Pages, repo `xotwod197/Ramiros_Portfolio`,
branch `main`, root folder. **Live:** https://xotwod197.github.io/Ramiros_Portfolio/

- Headline on the site and résumé: **"IT Systems Administrator | Network Support"**. Job title in
  Experience stays **Help Desk Technician** at WCMagnetics (full-time); Target General
  Merchandise Expert (part-time). No schedule days.
- Public handles: GitHub `xotwod197`, LinkedIn `ramirooherrera`.
- No custom domain yet (`ramiroomarherrera.com` was tried in Pages settings without owning it;
  `ramiroherrera.com` / `ramiroh.com` were earlier ideas). Don't add a `CNAME` until one is bought.

## Files

| File | Purpose |
|---|---|
| `index.html` | Home: PowerShell-console hero, About, Skills, Experience, short featured-projects teaser, Certifications & education, printable Résumé section, Links, Contact. |
| `projects.html` | All projects with screenshot galleries. Filter All / At WCMagnetics / Personal builds (kept in the URL hash, e.g. `projects.html#work`). |
| `site.css` | Shared stylesheet for both pages — design tokens, layout, motion, print rules. |
| `glass.css` | Windows 11 (Fluent) glass layer loaded after `site.css` on both pages — wallpaper, frosted panels, rounded/pill shapes. |
| `ramiro-herrera-resume.pdf` | Downloadable résumé, **regenerated from `index.html#resume`** whenever the résumé changes so the two never drift. Linked next to the Print / Save as PDF button. |
| `og-image.png` | 1200×630 share preview, Windows 11 style (PowerShell window on bloom wallpaper). |
| `images/` | Profile photo + project screenshots (`.webp` preferred). No duplicate image files. |
| `.github/screenshots/` | Before/after shots used in PR descriptions only. |
| `README.md` | Public description of the site, files, editing and deployment. |

## Where things live

- **Work PC git clone:** `C:\My Apps\Ramiro's Portfolio\` — edit here, commit, push. GitHub Pages
  rebuilds `main` automatically.
- **Home PC git clone:** `C:\Users\miroh\Documents\Websites\Portfolio\` (cloned 2026-10-15).
  Ramiro pushes from PowerShell there (`git push origin main`); no GitHub Desktop on this PC.
- `IMG_0745.JPG` in the home clone is a local-only source photo — it is in `.git/info/exclude`
  and must never be committed. The site photo is `images/profile.jpg`.
- Job-tailored previews live **outside** the repo (in `Documents\Websites\`) so they can never
  be pushed.
- Two Claude accounts are used (work + home). Neither can see the other's chat history — this
  file is the shared memory.

## Design

- v2 "console" design (adopted Oct 2026, Ramiro loves it): light mode, PowerShell-console hero,
  sticky sidebar nav, Geist + JetBrains Mono (restyled from Bricolage Grotesque + IBM Plex Mono),
  teal accent, wide fluid layout, circular profile photo next to the name.
- Phone layout: menu button, headline first, shorter page, tighter console block.
- Projects page: Quick Look / Apple Photos-style screenshot viewer (large image over the blurred
  page, filmstrip of the other views, spring open/close), draggable + scrollable thumbnail strips.
- **Glass look — Windows 11 Fluent (adopted 2026-10-16):** Ramiro's experience is Windows, so the
  site leans Windows, not Mac, while keeping the Apple-like polish (glass, springs, pill buttons).
  Windows 11 light "bloom" blue wallpaper (fixed), Mica/acrylic frosted panels (`backdrop-filter`
  blur + saturate, white edge, soft shadow), Windows-style rounded corners (panels 12px, nav items
  8px, console window 8px). Buttons / chips / filters stay pill-shaped, sidebar icons circular.
  Console = Windows PowerShell window: PS icon + title left, minimize / maximize / close right
  (close hovers red). **No Mac traffic-light dots.** Nav current section = Windows 11 Settings
  style: soft grey tint + short teal bar on the left that stretches while the pill slides.
  Desktop sidebar is a floating rounded glass panel; phone header a floating glass bar. Plain
  white fallback under `prefers-reduced-transparency`; print stays plain. All in `glass.css`.
  (A macOS version came first on 2026-10-15 and was replaced.)
- **Motion (Oct 2026):** subtle, Apple-feel but not obviously Apple. Spring easing
  (`--ease-spring`, reuses `--lb-spring`) for movement, `--ease-out` for colour/shadow. Hover =
  small lift (buttons 1px, sidebar icons 2px, link cards 3px) + soft `--shadow-lift`; lifts only
  inside `@media (hover: hover)` so phones don't get sticky hovers. Press = quick shrink
  (0.92–0.985) that springs back. Home nav has one sliding "pill" (styled by `glass.css` as a rounded teal tint) that
  follows the scrollspy section; `projects.html` keeps the static teal border. Every motion is
  switched off under `prefers-reduced-motion`; print layout unaffected. All in the MOTION block
  of `site.css`.
- **Cache-busting:** the `site.css` / `glass.css` links carry `?v=YYYYMMDD`; bump it whenever
  either stylesheet changes so visitors don't get old CSS with new HTML.
- **Constraints:** no external dependencies besides Google Fonts; any PowerShell shown must be
  **PS 5.1 compatible**; keep anchor IDs `#about #skills #experience #projects #certifications
  #resume #links #contact`.

## Content rules — these are firm

- **Naming in public:** the task tracker is **"My Task App"** / "Task App" (never "Flux"); the
  notes app is **"MyNotes"** / "my notes app" (never "WCM Notes"); the help-desk tool is
  **"ProTight (ProSuite)"** (not ConnectWise ProSuite).
- **Certs:** A+ shown as earned **2026**, no month. Network+ and CCNA shown as in progress.
- **About:** stat card is **200+ computers / 100+ users**. Do **not** feature the 100+
  Windows 10→11 upgrades there.
- **Projects page = exactly these 10 cards** (don't add others unless Ramiro names them):
  WCM Toolbox · WCM IP Scanner · Silent Deployments (SOLIDWORKS, Windows 11, WorldShip,
  Printers) · Lab Instrument Automation & Support · Employee Onboarding Document Suite ·
  Shift Dashboard & Status Board · My Task App · MyNotes · Pocket (phone-first money tracker) ·
  Home Lab.
- **Removed on purpose — never re-add** (home page, projects page, résumé section, or PDF):
  Sage 100 activity dashboard, Photo Wall, CCNA study console, CompTIA A+/Network+ study hubs,
  production work-instruction kiosks, hard-problem case files, the shared-account sign-in
  tracker, and the OneDrive folder rollback.
- **Links:** no per-project source links on cards; GitHub is one general profile link.
  Screenshots only.
- **Screenshots must be sanitised:** pixelate/censor default passwords, Sage logins, VPN guide
  names, and **all** company contact details — phone numbers and extensions, emails, street
  address / PO box, `www.wcmagnetics.com` and portal links — including in footers and letterhead.
  Demo data where possible.
- **Résumé stays consistent with the site.** Two pages is fine. Regenerate the PDF after any
  résumé edit. (Home PC method: headless Chromium print of `index.html#resume`, Letter, scale
  0.83, margins 0.45in top/bottom and 0.55in sides, pages 1–2.)
- When tailoring for a job, build a preview copy outside the repo first; only change the live
  site once Ramiro approves.
- Home page shows only a short featured teaser (WCM Toolbox & IP Scanner, My Task App, MyNotes);
  the full list lives on `projects.html`.

## Changelog (newest first)

### 2026-10-16 (home PC via Claude, Projects)
- Share image `og-image.png` redone in the Windows 11 style: bloom wallpaper behind a Windows
  PowerShell window (minimize / maximize / close), name, headline, focus, certs, site URL.
  `og:image` / `twitter:image` URLs now end in `?v=YYYYMMDD` so LinkedIn and others refetch;
  bump it whenever the image changes.
- Windows 11 restyle (approved from a preview in `Documents\Websites\Portfolio-windows-preview\`):
  console title bar now Windows PowerShell with minimize / maximize / close instead of Mac dots;
  bloom-blue wallpaper, 12px Fluent corners, Windows 11 Settings-style nav indicator. Changed
  `glass.css` and the console markup in `index.html`. No content or résumé changes.
- Nav highlight fix: on the live site the sliding pill sat below the nav list (under Contact).
  Cause: a cached old `site.css` with the new script, so the pill measured from the sidebar
  instead of the list. Pill now measures against the list with `getBoundingClientRect`, forces
  the list to `position: relative`, and re-measures after fonts load. Stylesheet links now carry
  `?v=YYYYMMDD` so browsers fetch fresh CSS after a push.

### 2026-10-15 (home PC via Claude, Projects)
- macOS glass restyle: new `glass.css` linked after `site.css` on `index.html` and
  `projects.html`. Ramiro first disliked the plain look with motion alone, approved the glass
  preview ("LOVE IT"). No content or résumé changes, so the PDF was not regenerated. Rules under
  Design → Glass look.
- Motion polish (uncommitted when written; Ramiro commits and pushes from PowerShell): spring
  hover/press on buttons, sidebar icon links, Links cards, nav links and the menu button; sliding
  active-section pill in the home-page sidebar nav (moves with the scrollspy, re-measures on
  resize and when the phone menu opens). Reduced-motion respected; phone layout and print
  checked. No content, headline or résumé changes, so the PDF was not regenerated. Motion rules
  recorded under Design.

### 2026-10-15 (home PC)
- Added this home-PC clone and the notes above; this changelog entry.
- `55eaa3e` Home + résumé: added hardware replacement, printers / Zebra label printers, barcode scanners,
  digital signage (dashboards and status boards on floor TVs/tablets) and client-side networking
  (DHCP, DNS, static IP) — new "hardware, printers & floor devices" duty group, new "Printers,
  scanners & signage" skill, résumé bullets and skills line. Tools chips: 10 highlighted (added
  Microsoft Office 365, Active Directory, Windows 11, "DHCP, DNS, Static IP", TCP/IP networking,
  Zebra, barcode scanners, digital signage). Headline unchanged. Résumé PDF regenerated (2 pages): to fit, the two
  PowerShell-tools bullets were merged into the WCM Toolbox bullet, the "Engineering & business
  applications" skills line was dropped, and Languages was shortened to one line.
- A job-tailored version with a different title was previewed but **not** adopted — Ramiro
  wants the site kept original, headline unchanged.
- LinkedIn (separate from the site, updated by Claude in Chrome): Help Desk Technician
  description and ~20 skills added on 2026-10-09; that description still mentions the removed
  work-instruction kiosks and needs a rewrite to match these rules. A mistaken "Ivanti" skill
  should be deleted.

### 2026-10-15 (work PC)
- `cb3d3a5` Projects: draggable, scrollable thumbnail strips.
- `6f54ce9` Projects: restored the Lab Instrument and Onboarding cards (dropped by mistake in
  the previous commit).
- `05a1920` Projects: Shift Dashboard & Status Board gallery with every status; dropped the
  sign-in tracker.
- `97063b3` / `cd198bc` Projects: sanitised screenshot gallery for the Employee Onboarding
  Document Suite card.
- `64bd251` Projects: sanitised screenshot gallery for the Lab Instrument Automation card.
- `339f879` Removed the retired projects from the home page and résumé section; regenerated
  `ramiro-herrera-resume.pdf`.
- `0e29128` Projects: removed six cards (see "Removed on purpose"), updated counts.
- `c5d267d` Projects: Quick Look-style screenshot viewer, gallery thumbnail styles, added the
  missing screenshots (Task App views, WCM Toolbox, WCM IP Scanner).
- `e3159ca` MyNotes card: four-view light-mode gallery.
- `e7164c7` **Split projects onto their own page** (`projects.html`, shared `site.css`), new
  work projects, updated skills/résumé, Task App screenshot.
- Added this `CLAUDE.md`.

### 2026-10-14 (evening, via PRs #1–#6)
- Phone layout: menu button, headline first, shorter page.
- Circular profile photo next to the name; larger name.
- README added.
- Restyle: Geist + JetBrains Mono, wider fluid layout, tighter phone terminal.
- Pocket card added; My Notes card updated for the online version.
- Source links dropped from project cards; screenshots only.
- Share preview `og-image.png` with `og:image` / `twitter:image`; canonical and `og:url` point
  at the GitHub Pages URL.

### 2026-09-23 → 2026-09-25
- v2 console redesign (`portfolio-v2.html` → `index.html`) adopted as the site; several
  upload/replace rounds; `CNAME` added and removed (no domain owned).

### 2026-03-11
- Initial v1 site (cream background, blue accent, DM Serif/DM Sans/DM Mono).

## Open items

- Custom domain: still choosing a name; nothing registered.
- Keep adding certs / projects / job changes as they happen — only ones Ramiro names.
