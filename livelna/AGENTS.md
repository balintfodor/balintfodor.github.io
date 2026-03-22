# AGENTS.md — Adsumfluo Landing Page

This file is for agentic coding assistants working in this repository.

---

## Project Overview

A static HTML landing page for **Adsumfluo**, a pre-launch SaaS for independent yoga/fitness instructors. The goal is to validate interest and collect email addresses. The page exists in two language versions: Hungarian (default) and English.

Full specifications live in five documents — read all of them before making changes:
- `BRIEF.md` — product purpose, target audience, constraints
- `COPY.md` — all final copy, must be used verbatim
- `DESIGN.md` — colour palette, typography, component specs
- `STRUCTURE.md` — section order, HTML patterns, form behaviour
- `TECH.md` — stack, file structure, image sourcing, performance targets

---

## Build / Lint / Test Commands

**There are no build tools, no npm, no package manager, no test framework.**

The project is intentionally zero-dependency. There is nothing to install or compile.

**To preview locally:**
```
open index.html        # macOS — opens in default browser
python3 -m http.server # optional: serve from localhost:8000
```

**To deploy:**
Push `index.html`, `en.html`, and `style.css` to the `main` branch of a GitHub repository with Pages enabled. No build step. Live within ~60 seconds.

**To validate:**
- Run Lighthouse in Chrome DevTools (target: performance score > 90 on mobile)
- Check both `index.html` and `en.html` manually in a browser
- Resize to below 600px width to verify mobile layout

---

## File Structure

```
/
├── index.html    — Hungarian (default)
├── en.html       — English
├── style.css     — Shared styles for both pages
├── AGENTS.md     — This file
├── BRIEF.md
├── COPY.md
├── DESIGN.md
├── STRUCTURE.md
└── TECH.md
```

No subfolders. No asset folder. Images load directly from Unsplash CDN.

---

## HTML Guidelines

- Use semantic HTML5 elements (`<main>`, `<nav>`, `<footer>`, `<blockquote>`, etc.)
- Include all meta tags in `<head>` as specified in `STRUCTURE.md` lines 129–136
- Include the GitHub Pages deploy comment block in `index.html` (`TECH.md` lines 63–73)
- The CTA area must use a `<div>` with `<input>` elements — **no `<form>` tag** (`STRUCTURE.md` line 106)
- Wrap the emphasised phrase in `<em>` with `font-style: normal; font-weight: 500` styling:
  - HU: wrap `"a te hangodon"` in `<em>`
  - EN: wrap `"in your own words"` in `<em>`
- Alt text for hero image (HU): `"Jógaoktató reggeli természetes fényben"`
- Alt text for hero image (EN): `"Yoga teacher in natural morning light"`
- Google Fonts must be loaded with the exact snippet from `TECH.md` lines 39–43 (preconnect + stylesheet)
- Load Google Fonts last among `<head>` links to avoid render blocking

---

## CSS Guidelines

- **No CSS variables** — use hardcoded hex values (`TECH.md` line 91)
- **No comments** in CSS (`TECH.md` line 90)
- **No `box-shadow`** anywhere (`DESIGN.md` line 148)
- **No gradients** (`DESIGN.md` line 149)
- **No animations or transitions** except button hover (background colour change only)
- **No dark mode** media query (`TECH.md` line 92)
- **Mobile-first** — base styles target mobile, single breakpoint at `600px`
- Max content width: `640px`, centered with `margin: 0 auto`
- Page padding: `1.5rem` mobile / `2rem` desktop

**Colour values (hardcoded, no variables):**
```
Background:       #F5F0E8
Text primary:     #2C2C2A
Text secondary:   #6B6B67
Text tertiary:    #9A9A95
Accent green:     #6B7B5E
Accent terracotta:#C17F5A
Border:           #E2DDD4
Surface:          #EDE8DF
```

**Typography:**
- `h1`: `DM Serif Display`, `400`, `2.4rem` mobile / `3rem` desktop, `line-height: 1.2`
- Section labels (`h2`): `DM Sans 500`, `0.7rem`, `uppercase`, `letter-spacing: 0.1em`, tertiary colour
- Feature titles: `DM Sans 500`, `0.95rem`
- Body: `DM Sans 400`, `1rem`, `line-height: 1.7`
- Small/captions: `DM Sans 400`, `0.8rem`

**Component specs (key measurements):**
- Email input: full width, `height: 42px`, `border-radius: 8px`, `border: 1px solid #E2DDD4`
- CTA button: background `#C17F5A`, hover `#A86D4A`, `border-radius: 8px`, `padding: 10px 22px`
- Feature icon box: `38px × 38px`, `background: #EDE8DF`, `border: 1px solid #E2DDD4`, `border-radius: 8px`
- CTA block: `background: #EDE8DF`, `border: 1px solid #E2DDD4`, `border-radius: 12px`, `padding: 2rem`
- Section dividers: `1px solid #E2DDD4`, `margin: 2.5rem 0`
- Vertical rhythm between sections: `3rem`

---

## JavaScript Guidelines

- **No comments** in JS (`TECH.md` line 90)
- **No libraries** — vanilla JS only
- Single responsibility: email validation + thank-you state + optional `localStorage` flag
- Inline `<script>` at the bottom of `<body>` or a minimal `script` block — no separate JS file needed

**Form validation logic (`STRUCTURE.md` line 107, `TECH.md` lines 51–54):**
1. On button click, validate email input is non-empty and contains `@`
2. If invalid: add red border to input, show inline error text below the input
3. If valid: hide form fields, show thank-you message in place (same padding as the form replaced)
4. Optionally store a `localStorage` flag to show a different state on return visits

**Error messages (exact strings):**
- HU: `"Kérjük, adj meg egy érvényes e-mail-címet."`
- EN: `"Please enter a valid email address."`

**Thank-you messages (exact strings):**
- HU: `"Köszönjük! Értesítünk, amikor elindul."`
- EN: `"Thank you! We will be in touch when it is ready."`

Thank-you message styling: `DM Sans 400`, `1rem`, text-secondary colour. No animation.

---

## Copy Rules

- All copy is final — use it **verbatim** from `COPY.md` (`COPY.md` line 3)
- Do not paraphrase, simplify, or "improve" any copy
- Hungarian is the default (`index.html`); English goes in `en.html` with identical structure
- Section order is fixed — follow `STRUCTURE.md` exactly

---

## Images

- Load directly from Unsplash CDN — **do not download images**
- URL format: `https://images.unsplash.com/photo-[ID]?w=1200&q=80&auto=format&fit=crop`
- Use **real Unsplash photo IDs** — never use placeholder services (picsum, placehold.it, etc.)
- Hero: yoga/fitness teacher in warm natural light, shot from behind or side, no phone visible
- Mid-page: instructor leaving a studio, coat and bag, unhurried
- Hero image: full width, `border-radius: 12px`, `aspect-ratio: 16/9` desktop / `4/3` mobile
- Mid-page image: same style, `aspect-ratio: 3/2`

---

## What to Avoid

- No product mockups or screenshots — product does not exist yet (`BRIEF.md` line 19)
- Do not mention AI prominently (`BRIEF.md` line 21)
- No corporate "we" language, no startup tone
- No Google Analytics, no tracking, no cookies, no cookie banner (`TECH.md` lines 87–89)
- No third-party scripts except Google Fonts
- No `<form>` element for the CTA — use `<div>` + `<input>` elements
- No separate JS file needed — keep JS inline and minimal
- Page should fit **one scroll on mobile** (`BRIEF.md` line 24)
- No language switcher UI in this version (`STRUCTURE.md` line 121)

---

## Responsive Layout

- Mobile-first CSS, single breakpoint: `@media (min-width: 600px)`
- Below 600px: email input and button stack vertically (full-width button)
- Above 600px: email input and button side by side in a flex row
- Headline: `2.4rem` below 600px, `3rem` above

---

## Performance Targets

- Lighthouse performance score > 90 on mobile
- Images use CDN width parameter (`?w=1200`) to avoid oversized assets
- Google Fonts loaded with `display=swap` to avoid render blocking
- No JavaScript libraries, no CSS frameworks, no bundler output
