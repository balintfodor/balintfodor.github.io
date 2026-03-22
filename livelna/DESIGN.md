# Adsumfluo — Design System

## Philosophy
This page should feel like a calm Sunday morning, not a startup landing page. No gradients, no animations, no hero illustrations. Warmth comes from typography, whitespace and a considered colour palette — not decoration.

The person reading this is a yoga teacher. She will notice if something feels corporate, rushed or fake. Everything should feel considered and unhurried.

---

## Colour palette

| Role | Hex | Usage |
|------|-----|-------|
| Background | #F5F0E8 | Page background — warm off-white, not pure white |
| Text primary | #2C2C2A | Headlines, strong text — near-black with warmth |
| Text secondary | #6B6B67 | Body text, descriptions |
| Text tertiary | #9A9A95 | Hints, captions, footer |
| Accent green | #6B7B5E | Feature icons, subtle accents |
| Accent terracotta | #C17F5A | CTA button background |
| Border | #E2DDD4 | Dividers, input borders, card borders |
| Surface | #EDE8DF | Feature cards, CTA block background |

No other colours. No blue. No purple. Nothing that looks like software.

---

## Typography

**Headline font:** DM Serif Display
- Load from Google Fonts
- Used only for the main headline h1
- Weight: 400 (the font is naturally strong)
- Size: 2.4rem mobile / 3rem desktop
- Line height: 1.2
- Colour: text primary

**Body font:** DM Sans
- Load from Google Fonts
- Used for everything else
- Weights: 400 (body) and 500 (labels, buttons, nav)
- Body size: 1rem / line height 1.7
- Subline size: 1.125rem / line height 1.7

**Scale:**
- h1: DM Serif Display, 2.4rem–3rem
- h2/section labels: DM Sans 500, 0.7rem, uppercase, letter-spacing 0.1em, colour tertiary
- Feature titles: DM Sans 500, 0.95rem
- Body: DM Sans 400, 1rem
- Small/captions: DM Sans 400, 0.8rem

---

## Layout

Max content width: 640px
Centered with auto margins
Page padding: 1.5rem mobile / 2rem desktop

Single column throughout. No grid. No sidebar. No columns.

Vertical rhythm: sections separated by 3rem. A thin 1px border (#E2DDD4) between major sections.

---

## Components

### Navigation
- Logo left: "Adsumfluo" in DM Sans 500, text primary
- Tag right: "Korai hozzáférés" / "Early access" — small pill, 0.7rem, border 1px solid border-colour, border-radius 20px, padding 3px 10px, text tertiary
- No links, no hamburger, no menu
- Margin bottom: 3.5rem

### Hero image placeholder
- A warm, naturally lit yoga or fitness instructor
- Shot from behind or at an angle — not posed, not performing
- No phone visible
- Warm sage greens, soft terracotta, morning light
- Full width, border-radius 12px, aspect ratio 16/9 on desktop, 4/3 on mobile
- Source: Unsplash — search "yoga teacher natural light studio"
- Use a real image, not a placeholder div

### Feature icons
- Simple single emoji per feature: 🎙 ✏️ 🌱
- Displayed in a 38x38px square, background surface colour, border 1px solid border-colour, border-radius 8px
- Font-size: 1rem inside the box

### Feature cards
- No card border or shadow
- Icon + text side by side, gap 1rem
- Feature title: DM Sans 500, 0.95rem, text primary
- Feature description: DM Sans 400, 0.875rem, text secondary, line-height 1.6
- Space between features: 1.75rem

### Blockquote
- Left border: 2px solid border-colour
- Padding left: 1.25rem
- Quote text: italic, 0.95rem, text secondary
- Attribution: 0.75rem, text tertiary, not italic

### CTA block
- Background: surface colour (#EDE8DF)
- Border: 1px solid border-colour
- Border-radius: 12px
- Padding: 2rem
- Title: DM Sans 500, 1.05rem, text primary
- Body: DM Sans 400, 0.875rem, text secondary

### Email input
- Full width
- Height: 42px
- Border: 1px solid border-colour
- Border-radius: 8px
- Background: #F5F0E8 (same as page)
- Font: DM Sans 400, 0.875rem
- Focus: border-colour darkens to #B8B0A4, no glow, no shadow

### CTA button
- Background: #C17F5A (terracotta)
- Colour: #FFFFFF
- Border: none
- Border-radius: 8px
- Padding: 10px 22px
- Font: DM Sans 500, 0.875rem
- Hover: background slightly darker (#A86D4A)
- On mobile: full width below the input

### Divider
- 1px solid #E2DDD4
- margin: 2.5rem 0
- No decorative elements

### Footer
- Text tertiary, 0.75rem, centered
- Dots as separators: ·
- Margin top: 3rem

---

## Responsive behaviour
- Mobile first
- Single breakpoint at 600px
- Below 600px: input and button stack vertically, headline slightly smaller
- Above 600px: input and button side by side in a flex row

---

## What to avoid
- No box shadows anywhere
- No gradients
- No animations or transitions except button hover (colour change only)
- No stock photo watermarks
- No placeholder grey boxes — use a real Unsplash image
- No dark mode
- No cookies, no tracking scripts, no analytics (keep it clean for now)
