# Adsumfluo — Technical Specification

## Stack
- Pure HTML5
- Pure CSS3 (no frameworks, no Tailwind, no Bootstrap)
- Vanilla JavaScript — minimal, only for the email form confirmation
- Google Fonts (DM Serif Display + DM Sans)
- Hosted on GitHub Pages

## File structure
```
/
├── index.html        (Hungarian — default)
├── en.html           (English)
├── style.css         (shared styles for both pages)
└── README.md         (optional, just a one-liner)
```

No subfolders. No assets folder. Images load from Unsplash CDN directly via URL.

---

## Images
Do not download images. Load directly from Unsplash using their CDN format:
```
https://images.unsplash.com/photo-[ID]?w=1200&q=80&auto=format&fit=crop
```

Find two suitable photos on unsplash.com:
1. Hero: yoga/fitness teacher in warm natural light, from behind or side, no phone visible
2. Mid-page: instructor leaving a studio, coat and bag, unhurried

Use real photo IDs. Do not use placeholder services like picsum or placehold.it.

---

## Google Fonts
Load in <head>:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500&family=DM+Serif+Display&display=swap" rel="stylesheet">
```

---

## Form behaviour
No backend. No form submission. No email service integration at this stage.

On button click:
1. Validate email field is not empty and contains @
2. If invalid: add a red border to the input, show inline error text below: "Kérjük, adj meg egy érvényes e-mail-címet." / "Please enter a valid email address."
3. If valid: hide the form fields, show thank-you message in their place
4. Store a flag in localStorage so returning visitors see a different state (optional — only if straightforward)

Thank you message styling:
- Same padding as the form it replaced
- Text: DM Sans 400, 1rem, text-secondary
- No animation, no confetti, no celebration

---

## GitHub Pages setup instructions (include as comment in index.html)
```
<!-- 
  To deploy:
  1. Create a new GitHub repository named: [username].github.io
     OR any repo name, then enable Pages in Settings > Pages > main branch
  2. Push index.html, en.html and style.css to the main branch
  3. Site is live at https://[username].github.io or https://[username].github.io/[reponame]
  No build step needed. Changes go live within 60 seconds of pushing.
-->
```

---

## Performance
- No JavaScript libraries
- No CSS frameworks
- Images load from CDN with width parameter (?w=1200) to avoid oversized assets
- Google Fonts loaded with display=swap to avoid render blocking
- Target: Lighthouse performance score above 90 on mobile

---

## Do not include
- Google Analytics or any tracking
- Cookie consent banner
- Any third-party scripts except Google Fonts
- Comments in CSS or JS (keep files clean)
- CSS variables (keep it simple and readable for easy editing)
- Dark mode media query
