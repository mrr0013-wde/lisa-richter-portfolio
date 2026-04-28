# Lisa Richter — Portfolio Site

A static, hand-built portfolio targeting Senior / Staff Product Designer roles at design-led companies, big tech, and product-led startups.

## What's inside

```
site/
├── index.html              Homepage — hero, selected work, impact, approach, contact
├── about.html              Full about page — story, timeline, skills, personality
├── work/
│   ├── shiftkey.html       Flagship case study (the $16M / 88K story)
│   ├── iknowmed.html       Ontada / McKesson — oncology EHR
│   ├── family-hub.html     Independent concept (in progress)
│   └── smashing-boxes.html Agency origin story
├── styles.css              Single-file design system
└── script.js               Reveal-on-scroll + nav state
```

## How to preview

**Option 1 — double-click.** Open `site/index.html` directly in your browser.

**Option 2 — local server (recommended).**
```bash
cd site
python3 -m http.server 5173
# Then open http://localhost:5173/
```

## How to deploy

This is a vanilla static site with no build step. Drag-and-drop deploy works on:

- **Vercel** — `vercel deploy` from the `site/` folder, or drag the folder into vercel.com/new
- **Netlify** — drag the `site/` folder into the Netlify dashboard
- **GitHub Pages** — push `site/` contents to a `gh-pages` branch
- **Cloudflare Pages** — connect repo, set publish dir to `site/`

## Design system

Single-file CSS at `styles.css`. Tokens are at the top of the file under `:root`:

- **Type:** Fraunces (display) + Inter (UI) + JetBrains Mono (numerics)
- **Color:** Warm cream `#FAF8F3`, deep ink `#1A1916`, terracotta accent `#D14A2A`, dark band `#161513`
- **Spacing:** 4px scale (`--sp-1` through `--sp-11`)
- **Motion:** Cubic-bezier ease curves; respects `prefers-reduced-motion`

To rebrand: change the CSS variables at the top of `styles.css`. Most of the site will follow.

## Where to put your real screenshots

Each case study has placeholder boxes with the class `.mockup`. Replace them with `<img>` tags:

```html
<img src="../images/shiftkey-onboarding-step-1.png" alt="ShiftKey onboarding step one — credential capture" />
```

Recommended image specs:
- Format: WebP (preferred) or PNG
- Width: 2400px for hero shots, 1600px for body shots
- Compression: ~80% quality

## Accessibility checklist

Built in:

- Skip-to-content link
- Semantic HTML (`<header>`, `<main>`, `<section>`, `<nav>`, `<article>`)
- Focus-visible rings (terracotta outline on tab navigation)
- `prefers-reduced-motion` respected
- Color contrast ≥ 4.5:1 for body text on cream background
- Images need `alt` text when you add real screenshots

Verify before launch:

- [ ] Run Lighthouse audit (target: 95+ across the board)
- [ ] Test with keyboard-only navigation
- [ ] Test with screen reader on at least one case study
- [ ] Verify in mobile Safari, Chrome, Firefox

## Content to fill in next

The flagship ShiftKey case study is fully written using your resume content. The other three (`iknowmed.html`, `family-hub.html`, `smashing-boxes.html`) have:

- Real context from your resume (companies, dates, role, scope, metrics)
- Full structure (Problem → Role → Process → Outcomes)
- Placeholders where deeper detail or visuals belong

Easiest order to fill in:
1. **iKnowMed** — flesh out specific Clinical Noting / Billing redesigns with screenshots
2. **Family Hub** — finish the design + write up the IA decision
3. **Smashing Boxes** — pick one client project to feature as the visual centerpiece

## Notes on positioning

The headline metric (**$16M revenue / 88K users**) is doing a lot of work. It's in:

- Hero stat strip on homepage
- Dark impact band on homepage
- Featured prominently on the ShiftKey case study card
- The outcomes section of the ShiftKey case study

If you ever update that number, search-and-replace `$16M` and `88K` across the site.

The site positions you as: **strategy + research + craft, with healthcare/EHR as your domain depth and AI-augmented design as your forward edge.** That positioning is woven through the hero copy, approach section, and Family Hub case study. If you want to shift it (e.g. lean harder into AI, or de-emphasize healthcare), the levers are: hero subhead, approach principles, and which case study sits in slot 01.
