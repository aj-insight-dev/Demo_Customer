# KC Cabinetry — Conscious Carpentry LLC

A 4-page static marketing site for KC Cabinetry (Conscious Carpentry LLC), a custom
finish cabinetry business serving Overland Park, Mission Hills, and greater Kansas City.

## Pages
| File | Purpose |
|------|---------|
| `index.html` | Restoration Showcase — main landing page, hero reel, smart storage, whole-home split, portfolio, 2026 Lookbook capture |
| `transitional.html` | Transitional style landing — why transitional, hidden functionality, portfolio, lookbook capture |
| `calculator.html` | Project Cost Calculator — 5-step live estimate + lead form |
| `assessment.html` | Refacing vs. Replacing — 3-question quiz + lead form + educational breakdown |

## Tech
Plain static HTML/CSS/JS — no build tooling or dependencies required to run.
- `styles/main.css` — full design system (cream / walnut / navy + gold; Fraunces + Mulish via Google Fonts)
- `scripts/main.js` — nav, scroll reveals, lightbox, calculator, quiz, form handling
- `favicon.svg` — procedural saw-blade + hammer mark
- `build.py` — optional generator that regenerates the 4 HTML pages from shared
  header/footer/emblem partials. Only needed if you want to edit shared chrome in one place.
  Run with `python3 build.py`.

## Assets (`assets/images/`)
- `projects/` — 14 optimized high-resolution project photos (descriptive filenames)
- `gallery/` — 19 portfolio thumbnails clipped from the Conscious Carpentry photo gallery
  (lower resolution; swap for high-res originals when available)
- `brand/logo-full.jpg` — the full logo (used in the footer)

## Run locally
Just open `index.html` in a browser, or serve the folder:
```
python3 -m http.server 8000
# visit http://localhost:8000
```

## Deploy
This is a static site — host it anywhere: Netlify, Vercel, Cloudflare Pages, GitHub Pages,
or any traditional web host. Drag-and-drop the whole folder, or point the host at this directory.

## TO FINISH BEFORE GOING LIVE
1. **Connect the forms to a CRM / email platform.** All four lead forms (lookbook, transitional
   lookbook, calculator, assessment) currently show a front-end confirmation only. Wire them up at
   the marked spot in `scripts/main.js` (search for `TODO: POST to CRM`). Easiest options:
   Formspree, Mailchimp embedded forms, HubSpot forms, or a Netlify Forms attribute.
2. **Transformation reel.** The homepage hero uses a CSS cross-fade slideshow as a stand-in for the
   15-second transformation video. Drop in the real video as a `<video autoplay muted loop>` background.
3. **Pull-out GIFs.** The transitional page uses still photos where animated GIFs of the pull-out
   pantry / spice rack were specced. Swap in the GIFs when available.
4. **Portfolio resolution.** The 19 portfolio tiles were clipped from Facebook gallery screenshots,
   so they're thumbnail quality. Replace with high-res originals for best results.
5. **Real BBB seal + privacy/terms pages.** Replace the styled "A+ BBB Accredited" badge with the
   official trademarked seal, and link the footer Privacy/Terms to real pages.
6. **Business name.** The site leads with "KC Cabinetry" and uses "Conscious Carpentry LLC" as the
   legal name in the header sub-label and footer. Flip if you'd prefer the LLC name to lead.

## Claude Code handoff
This prototype is ready to hand to Claude Code for the production build. Good next steps there:
- Convert shared chrome to includes/templates (or a static site generator like Eleventy) instead of `build.py`.
- Wire the forms to your chosen CRM and add server-side validation + spam protection.
- Add real meta/Open Graph tags, a sitemap, `robots.txt`, and analytics.
- Add the transformation video and pull-out GIFs.
- Run Lighthouse and tune performance/SEO/accessibility.
