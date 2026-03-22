# Adsumfluo — Page Structure

Build a single HTML file: index.html
One CSS file: style.css
No JavaScript frameworks. Vanilla JS only, minimal.
No build tools. No npm. No dependencies except Google Fonts.

---

## Section order

1. Navigation
2. Hero image
3. Headline + subline
4. Divider
5. Three features
6. Divider
7. Mid-page image + quote
8. Divider
9. Website section
10. Divider
11. CTA block (email capture)
12. Footer

---

## Section 1 — Navigation
```
[Adsumfluo]                    [Korai hozzáférés]
```
Logo left, pill tag right. No links.

---

## Section 2 — Hero image
Full width image, border-radius 12px.
Alt text: "Jógaoktató reggeli természetes fényben" (HU) / "Yoga teacher in natural morning light" (EN)
Source: Unsplash (see DESIGN.md for search terms)

---

## Section 3 — Headline + subline
h1: main headline
p: subline with one <em> span around the emphasised phrase:
- HU: wrap "a te hangodon" in <em>
- EN: wrap "in your own words" in <em>
em styling: font-style normal, font-weight 500, colour text-primary

---

## Section 4 — Divider

---

## Section 5 — Three features
Section label above: "Hogyan működik" / "How it works"
Three feature rows, each:
  [icon box]  [title]
              [description]

Features in order:
1. 🎙 Capture (HU: Rögzítsd / Kapd el a gondolatot)
2. ✏️ Shape (HU: Alakítsd)
3. 🌱 Show up (HU: Jelenj meg)

All copy from COPY.md — use exactly as written.

---

## Section 6 — Divider

---

## Section 7 — Mid-page image + quote
Second image: same style as hero, slightly shorter aspect ratio (3/2)
Search terms: "yoga instructor bag coat leaving studio"

Below image, blockquote with attribution.
Copy from COPY.md.

---

## Section 8 — Divider

---

## Section 9 — Website section
Section label: "A saját helyed az interneten" / "Your own corner of the internet"
Two paragraphs. Copy from COPY.md exactly.

---

## Section 10 — Divider

---

## Section 11 — CTA block
Inside the surface-coloured card:

Title (p, not h)
Body text
Email input + button (flex row, stacks on mobile)
Optional question label + hint
Optional text input (full width)

No form tag. Use div with inputs.
Button click: simple JS that shows a thank-you message inline, replaces the button. No backend, no API. Just a localStorage flag and a gentle confirmation message.

Thank you message HU: "Köszönjük! Értesítünk, amikor elindul."
Thank you message EN: "Thank you! We will be in touch when it is ready."

---

## Section 12 — Footer
Single line, centered.
Copy from COPY.md.

---

## Language switching
No visible language switcher on this version.
Build Hungarian as the default (index.html).
Build English as a separate file (en.html) with identical structure, English copy from COPY.md.
Link between them only if asked later.

---

## Meta tags (include in <head>)
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Adsumfluo — Legyél ott a tanítványaidnak</title>
<meta name="description" content="Mondd el, ami az óra után eszedbe jut. Abból lesz egy poszt, egy weboldal-frissítés, egy üzenet — a te hangodon, egyetlen érintéssel.">
<meta property="og:title" content="Adsumfluo">
<meta property="og:description" content="Legyél ott a tanítványaidnak — akkor is, ha épp nem tanítasz.">
<meta property="og:type" content="website">
```
