# Mizpah Lodge #302 — Design System
**mizpahomaha.com** · Omaha, Nebraska · Est. 1919

> A century-old Masonic lodge. Dark, dignified, and community-rooted. Deep navy backgrounds with warm gold accents, serif heritage typography paired with clean sans-serif body text — authoritative without being cold, historic without being stale.

---

## 1. Visual Theme & Atmosphere

### Overall Aesthetic
Mizpah Lodge embodies **Masonic tradition meets accessible community presence**. The interface feels like the lodge itself — dark wood paneling, candlelight gold, and the quiet gravity of a century-old institution. Every element communicates dignity and brotherhood while remaining welcoming to prospective members and community visitors who may know nothing about Freemasonry.

### Mood & Feeling
- **Dignified heritage**: Dark backgrounds evoke lodge room atmosphere and institutional gravity
- **Warm invitation**: Gold accents soften the darkness, signaling welcome rather than exclusivity
- **Community anchor**: Design reflects that this is a neighborhood institution, not a private club
- **Timeless craftsmanship**: Typography and layout reference the stonemason tradition — measured, deliberate, built to last
- **Editorial depth**: Rich historical content deserves generous spacing and clear hierarchy

### Design Density
**Low-to-medium density** with deliberate breathing room. Navigation is compact; content sections are generous. Cards and info panels use internal padding to prevent the dark background from feeling oppressive.

### Visual Character
- Deep navy/dark backgrounds (`#0d1b2a` range) as the dominant foundation
- Warm gold (`#c9a84c`) as the singular brand accent — used for borders, highlights, active states, and key UI moments
- Off-white/warm light text (`#e8e8e8`, `#d4c5a9`) for readability against dark surfaces
- Alegreya serif for display and headings — classical, scholarly weight
- Roboto sans-serif for body, labels, and UI — clean counterbalance
- Subtle gold dividers (`border-bottom: 1px solid rgba(201,168,76,0.3)`) used throughout
- Cards use slight background lift (`rgba(255,255,255,0.06)`) over dark base
- Minimal shadows — depth created through tonal shifts and border contrast
- Border-radius: 5–8px — approachable but not playful

---

## 2. Color Palette & Roles

### Core Foundation

| Token | Hex / Value | Role |
|-------|-------------|------|
| `--bg-primary` | `#0d1b2a` | Page background (deep navy) |
| `--bg-surface` | `#1a1a2e` | Cards, panels, elevated surfaces |
| `--bg-surface-hover` | `rgba(255,255,255,0.09)` | Hovered inputs and interactive surfaces |
| `--bg-alt` | `rgba(255,255,255,0.06)` | Subtle surface differentiation within cards |
| `--text-primary` | `#e8e8e8` | Primary body text |
| `--text-warm` | `#d4c5a9` | Warm secondary text, descriptions |
| `--text-light` | `#aaaaaa` | Tertiary text, metadata, captions |

### Brand Colors

| Token | Hex / Value | Role |
|-------|-------------|------|
| `--gold` | `#c9a84c` | Primary accent — borders, headings, active nav, labels |
| `--gold-hover` | `#e0b956` | Gold hover state — buttons, links |
| `--gold-subtle` | `rgba(201,168,76,0.15)` | Gold tint backgrounds (stepper buttons, tags) |
| `--gold-border` | `rgba(201,168,76,0.35)` | Standard card/input borders |
| `--gold-divider` | `rgba(201,168,76,0.3)` | Section dividers within cards |
| `--gold-strong` | `rgba(201,168,76,0.5)` | Emphasized dividers, setup banners |

> **Note:** Gold (`#c9a84c`) is the ONLY accent color in the current palette. There is no secondary brand color defined. All interactive highlights, labels, borders, and UI moments use gold or a gold variant. Do not introduce blue, teal, purple, or other accent colors without an explicit design decision.

### Payment Button Colors (contextual only)

| Token | Hex | Role |
|-------|-----|------|
| `--paypal-blue` | `#003087` | PayPal brand button background |
| `--venmo-blue` | `#008CFF` | Venmo brand button background |

These are third-party brand colors used only on payment CTAs. They are not part of the lodge palette.

### Semantic Colors

| Token | Hex / Value | Role |
|-------|-------------|------|
| `--success-bg` | `rgba(72,187,120,0.15)` | Form success state background |
| `--success-border` | `rgba(72,187,120,0.5)` | Form success state border |
| `--success-text` | `#68d391` | Success message text |
| `--error-bg` | `rgba(245,101,101,0.12)` | Form error state background |
| `--error-border` | `rgba(245,101,101,0.4)` | Form error state border |
| `--error-text` | `#fc8181` | Error message text |

---

## 3. Typography Rules

### Font Stack

```css
/* Display & Headings */
--font-serif: 'Alegreya', Georgia, 'Times New Roman', serif;

/* Body, UI, Labels */
--font-sans: 'Roboto', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
```

Both loaded via Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=Alegreya:ital,wght@0,400;0,700;1,400&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
```

### Type Scale

| Element | Size | Weight | Font | Color |
|---------|------|--------|------|-------|
| Hero H1 | 2.8–3.2rem | 700 | Alegreya | `#e8e8e8` |
| Page H1 | 2rem | 700 | Alegreya | `--gold` |
| Section H2 | 1.5rem | 700 | Alegreya | `--gold` |
| Card H3 | 1.1–1.5rem | 700 | Alegreya | `--gold` |
| Nav links | 0.9rem | 400 | Roboto | `#e8e8e8` |
| Body | 0.95–1rem | 400 | Roboto | `#e8e8e8` |
| Labels (form) | 0.8rem | 500 | Roboto | `--gold` |
| Small/caption | 0.85–0.9rem | 400 | Roboto | `--text-light` |
| Button | 0.95–1rem | 700 | Roboto | `#111` on gold |

### Typography Philosophy
Alegreya is used exclusively for headings and display text — it carries the historical, fraternal weight of the lodge. Roboto handles all functional UI: navigation, body copy, form labels, and buttons. **Never use Alegreya for UI elements (buttons, labels, inputs).** Never use Roboto for section or card headings. The contrast between the two is intentional and central to the design identity.

Headings in gold on dark backgrounds are a signature pattern. Labels above form fields are uppercase, 0.8rem, letter-spaced (~0.06em), in gold — a recurring motif across the site.

---

## 4. Component Patterns

### Navigation Header

```
Background: dark navy (matches --bg-primary)
Logo: left-aligned image (images/header_miz.png)
Nav links: Roboto 0.9rem, #e8e8e8, uppercase or mixed case
Active link: class="active", color --gold
Donate button: class="btn-donate", gold border + text, transparent bg
Mobile: hamburger toggle (.nav-toggle), nav slides in with class="open"
Dropdown: .has-dropdown > .dropdown, shown on hover (desktop) or tap (mobile)
```

### Page Header Banner

Used on all inner pages (not homepage):
```
Background: slightly lighter than page bg, or dark with subtle gradient
H1: Alegreya, ~2rem, gold or white
Subtitle p: Roboto, 0.95rem, --text-warm or --text-light
Padding: generous vertical (40–60px)
```

### Cards / Info Cards (.info-card)

```css
.info-card {
  background: var(--bg-surface);       /* #1a1a2e */
  border: 1px solid var(--gold-border); /* rgba(201,168,76,0.35) */
  border-radius: 8px;
  padding: 32px;
}

.info-card h3 {
  font-family: 'Alegreya', serif;
  color: var(--gold);
  font-size: 1.5rem;
  margin-bottom: 20px;
  padding-bottom: 12px;
  border-bottom: 1px solid var(--gold-divider);
}
```

### Buttons

#### Primary (Gold fill)
```css
.btn-primary {
  background: var(--gold);       /* #c9a84c */
  color: #111;
  font-family: 'Roboto', sans-serif;
  font-weight: 700;
  padding: 12–14px 20–24px;
  border-radius: 6px;
  border: none;
  transition: background 0.2s, transform 0.15s;
}
.btn-primary:hover {
  background: var(--gold-hover); /* #e0b956 */
  transform: translateY(-1px);
}
```

#### Outline (Ghost gold)
```css
.btn-outline {
  background: transparent;
  color: var(--gold);
  border: 1px solid var(--gold);
  border-radius: 6px;
  font-family: 'Roboto', sans-serif;
  font-weight: 500;
}
.btn-outline:hover {
  background: var(--gold-subtle);
}
```

#### Donate (nav button)
```css
.btn-donate {
  border: 1px solid var(--gold);
  color: var(--gold);
  border-radius: 4px;
  padding: 6px 14px;
  font-size: 0.85rem;
}
.btn-donate:hover {
  background: var(--gold);
  color: #111;
}
```

### Form Inputs

```css
input, select, textarea {
  background: rgba(255,255,255,0.06);
  border: 1px solid var(--gold-border);
  border-radius: 5px;
  color: #e8e8e8;
  font-family: 'Roboto', sans-serif;
  padding: 11px 14px;
}
input:focus, select:focus, textarea:focus {
  border-color: var(--gold);
  background: rgba(255,255,255,0.09);
  outline: none;
}
```

Form labels:
```css
label {
  font-family: 'Roboto', sans-serif;
  font-size: 0.8rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--gold);
}
```

### Dividers

The standard decorative divider used beneath section headings:
```css
.divider {
  width: 60px;
  height: 2px;
  background: var(--gold);
  margin: 12px auto;
}
```

### Tables (.dues-table)

```css
thead th {
  background: rgba(201,168,76,0.15);
  color: var(--gold);
  font-family: 'Roboto', sans-serif;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 0.8rem;
}
tbody td {
  border-bottom: 1px solid rgba(201,168,76,0.15);
  color: #e8e8e8;
}
tr.total-row td {
  color: var(--gold);
  font-weight: 700;
  border-top: 1px solid var(--gold-border);
}
```

### Blockquotes / Pull Quotes

Used on the About page for historical quotes:
```css
blockquote {
  border-left: 3px solid var(--gold);
  padding-left: 20px;
  font-family: 'Alegreya', serif;
  font-style: italic;
  color: var(--text-warm);
  margin: 24px 0;
}
```

### Status Messages (forms)

```css
.form-status {
  display: none;              /* hidden by default — shown via JS only */
  padding: 14px 18px;
  border-radius: 6px;
  margin-top: 16px;
  font-family: 'Roboto', sans-serif;
  font-size: 0.95rem;
}
/* JS sets display:block when shown — do NOT use display:block in CSS modifiers */
.form-status.success {
  background: rgba(72,187,120,0.15);
  border: 1px solid rgba(72,187,120,0.5);
  color: #68d391;
}
.form-status.error {
  background: rgba(245,101,101,0.12);
  border: 1px solid rgba(245,101,101,0.4);
  color: #fc8181;
}
```

---

## 5. Layout & Spacing

### Page Structure

```
<header class="site-header">        ← injected via header.html + js/header-loader.js
<div class="page-header">           ← inner page banner (not on homepage)
<section class="content-page">      ← main content wrapper
  <div class="container">           ← max-width constrained, centered
<footer class="site-footer">
```

### Container

```css
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 24px;
}
```

### Spacing Scale (approximate)

| Token | Value | Usage |
|-------|-------|-------|
| `--space-xs` | 8px | Tight gaps, inline elements |
| `--space-sm` | 12–16px | Between related elements |
| `--space-md` | 20–24px | Card padding, section gaps |
| `--space-lg` | 32px | Card padding (desktop) |
| `--space-xl` | 40–48px | Between major sections |
| `--space-2xl` | 60–80px | Hero sections, page headers |

### Grid Patterns

Two-column grid (primary layout for RSVP, contact, welcome section):
```css
.two-col {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
}
@media (max-width: 768px) {
  .two-col { grid-template-columns: 1fr; gap: 24px; }
}
```

Payment/feature cards (three-up):
```css
.three-col {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
@media (max-width: 768px) {
  .three-col { grid-template-columns: 1fr; }
}
```

### Breakpoints

| Name | Value | Behavior |
|------|-------|----------|
| Mobile | `≤ 768px` | Single column, hamburger nav |
| Tablet | `769px–1024px` | Transitional |
| Desktop | `≥ 1024px` | Full multi-column layouts |

---

## 6. Shared Infrastructure

### Header Include System

The site uses a JS-fetched shared header to avoid duplicating nav across pages:

```
header.html          ← single source of truth for nav markup
js/header-loader.js  ← fetches header.html, injects it, sets active link, wires mobile nav
```

Every page body opens with:
```html
<div id="site-header"></div>
```

And closes with:
```html
<script src="js/header-loader.js"></script>
```

Active nav state is set dynamically by matching `window.location.pathname` to link `href` — **never hardcode `class="active"` in page files**.

### Data Collection

RSVP form (`rsvp.html`) submits to Google Apps Script:
```
https://script.google.com/macros/s/AKfycbyw_.../exec
```
Uses `fetch()` with `mode: 'no-cors'`. Responses land in a Google Sheet.

Payment links:
- PayPal: `https://www.paypal.me/mizpah302`
- Venmo: `https://www.venmo.com/u/mizpah302`

---

## 7. Voice & Copy Tone

- **Formal but warm** — never stuffy, never casual
- **Brotherhood is assumed** — write as if addressing someone who belongs or wants to
- **History is an asset** — dates, names, and milestones are used actively, not stored in footers
- **Community service is core** — not a footnote; woven into page content
- Page subtitles are short and purposeful (e.g., *"Join our Brotherhood & support our community"*)
- CTAs are action-first: "Reserve Your Seat", "Download Petition Form", "Contact the Secretary"

---

## 8. Agent Prompt Reference

Use this block when prompting Claude Code to build or modify pages for this site:

```yaml
# Mizpah Lodge #302 — mizpahomaha.com

## Identity
Masonic lodge, Omaha Nebraska, founded 1919.
Dark navy aesthetic, gold accents, serif/sans type pairing.

## Colors
Background: #0d1b2a (page) / #1a1a2e (cards/surfaces)
Gold accent: #c9a84c (borders, headings, labels, active states)
Gold hover: #e0b956
Gold border: rgba(201,168,76,0.35)
Gold divider: rgba(201,168,76,0.3)
Text primary: #e8e8e8
Text secondary: #d4c5a9
Text tertiary: #aaaaaa

## Typography
Headings: Alegreya serif, color --gold or #e8e8e8
Body/UI: Roboto sans-serif, color #e8e8e8
Form labels: Roboto 0.8rem, 500 weight, uppercase, letter-spacing 0.06em, color --gold
Never use Alegreya for buttons or form labels.
Never use Roboto for section headings.

## Components
Cards: bg #1a1a2e, border rgba(201,168,76,0.35), border-radius 8px, padding 32px
Primary button: bg #c9a84c, color #111, Roboto bold, hover #e0b956
Inputs: bg rgba(255,255,255,0.06), border rgba(201,168,76,0.35), focus border #c9a84c
Blockquotes: border-left 3px solid #c9a84c, Alegreya italic
Status messages: hidden by default (display:none), shown via JS (display:block) — never set display:block in CSS modifiers

## Shared Header
All pages use <div id="site-header"></div> + <script src="js/header-loader.js"></script>
Never hardcode the <header> block in page files.
Never hardcode class="active" on nav links — the loader sets this dynamically.

## Fonts (Google Fonts)
Alegreya: ital,wght@0,400;0,700;1,400
Roboto: wght@300;400;500;700

## Layout
Container: max-width 1100px, centered, padding 0 24px
Mobile breakpoint: 768px (single column, hamburger nav)
Primary grid: 1fr 1fr, gap 40px, collapses to 1fr at 768px

## Domain
mizpahomaha.com (GitHub Pages, custom domain)
Repo: github.com/Axeion/omahamasons
```

---

## 9. Pages Reference

| File | Nav Label | Purpose |
|------|-----------|---------|
| `index.html` | Home | Hero, pillars, WM message, what is Freemasonry, appendent bodies |
| `about.html` | About | Lodge history, MWB Futcher legacy, centennial, community partnerships |
| `calendar.html` | Calendar | Google Calendar embed + Trestle Board link |
| `trestle-board.html` | *(dropdown)* | Newsletter archive |
| `scholarships.html` | Membership | Petition for initiation + scholarship applications |
| `dues.html` | Lodge Dues | Annual dues breakdown + payment methods |
| `club-1919.html` | Club 1919 | Voluntary $19.19/mo charitable giving program |
| `contact.html` | Contact Us | Contact form (Formspree) + lodge info + map |
| `shop.html` | Shop | Etsy storefront link |
| `rsvp.html` | Dinner RSVP | Monthly business meeting dinner RSVP + PayPal/Venmo payment |
| `header.html` | *(include)* | Shared nav — injected by header-loader.js |
| `js/header-loader.js` | *(script)* | Fetches header.html, sets active state, wires mobile nav |
