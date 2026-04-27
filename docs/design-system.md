# Design System

Status: **draft** — reconciled against the Claude Design handoff (preserved in `docs/handoff/`). Driven by `docs/brand-guidelines.md`.

The Collective's job is to bridge two distinct vendor brands without flattening either. That shapes the system: we keep three palettes (Collective + Starving Dragon + Ridge & Valley), each with its own tokens, and the Collective's surface stays warm/earthy/calm so vendor accents can sit on top without clashing.

If something here starts feeling slick or corporate, it's wrong. If something starts feeling like a unified brand layer over the vendors, that's also wrong.

---

## Palette

Three sets of tokens, prefixed by brand. Use the prefix everywhere (no aliasing into a single neutral set) so vendor pages can subtly shift accent colors without leaking across.

### Chattanooga Collective (`--cc-*`)

Adopted from the design handoff verbatim (we agreed it's better calibrated than my earlier draft).

| Token | Hex | Use |
| --- | --- | --- |
| `--cc-bg` | `#f5f0e8` | Default page background — warm parchment |
| `--cc-bg-section` | `#ede6d8` | Alternating section, vendor-grid surface |
| `--cc-bg-card` | `#faf7f2` | Card / floating element |
| `--cc-bg-dark` | `#2a2018` | Deep wood — footer, dark sections |
| `--cc-text-1` | `#1e1a14` | Body / headings |
| `--cc-text-2` | `#3d3020` | Strong-emphasis body |
| `--cc-text-3` | `#6a5438` | Default body color (warm brown) |
| `--cc-text-4` | `#9a7d58` | Muted tan, captions |
| `--cc-text-5` | `#bda882` | Lightest readable on dark |
| `--cc-text-inv` | `#f5f0e8` | Text on `--cc-bg-dark` |
| `--cc-green` | `#3a5c3a` | Primary accent — links, primary buttons |
| `--cc-green-light` | `#5a8a4a` | Hover for `--cc-green` |
| `--cc-ochre` | `#c4831a` | Secondary accent — eyebrow labels, dividers |
| `--cc-ochre-light` | `#e8a83a` | Decorative — radial gradient stops |
| `--cc-rust` | `#a04520` | Tertiary — used sparingly, e.g., inline emphasis |
| `--cc-rust-light` | `#c86040` | Hover for `--cc-rust` |
| `--cc-border` | `rgba(60,40,10,0.12)` | Subtle dividers |
| `--cc-border-mid` | `rgba(60,40,10,0.22)` | Card / nav borders |
| `--cc-border-accent` | `rgba(164,100,32,0.30)` | Accent borders (rare) |

### Starving Dragon (`--sd-*`)

Adopted from the vendor's existing site. Don't change without their sign-off.

| Token | Hex | Use |
| --- | --- | --- |
| `--sd-bg` | `#0d0703` | Primary dark background |
| `--sd-bg-section` | `#110904` | Alternate section |
| `--sd-bg-footer` | `#080402` | Deepest dark |
| `--sd-accent` | `#e8522a` | Chili red-orange — accent everywhere |
| `--sd-accent-dark` | `#c43d1a` | Hover |
| `--sd-accent-glow` | `rgba(200,60,10,0.20)` | Hero radial glow |
| `--sd-text-1`–`--sd-text-7` | `#f5ede0` → `#705028` | Warm cream → muted brown ramp (7 stops) |
| `--sd-border` | `rgba(200,80,20,0.12)` | Subtle warm border |
| `--sd-border-mid` | `rgba(200,80,20,0.20)` | Nav bottom |
| `--sd-border-hover` | `rgba(232,82,42,0.40)` | Card hover |
| `--sd-icon-bg` | `rgba(232,82,42,0.08)` | Feature icon background |
| `--sd-icon-border` | `rgba(232,82,42,0.18)` | Feature icon border |

For the *Collective's* Starving Dragon vendor card, only `--sd-accent` (`#e8522a`) crosses into the Collective surface — used for the card's top border and "Order yours" link color. The dark backgrounds stay on starvingdragon.com.

### Ridge & Valley (`--rv-*`)

**Proposed — needs vendor sign-off.** Carries the Appalachian-rooted, functional/wellness direction from the brand guide. From the design handoff verbatim; safe to iterate once R&V validates.

| Token | Hex | Use |
| --- | --- | --- |
| `--rv-bg` | `#f2f5ee` | Cool sage white |
| `--rv-bg-section` | `#e4ebe0` | Light sage |
| `--rv-bg-dark` | `#1e2a1e` | Deep forest |
| `--rv-bg-card` | `#ffffff` | Card |
| `--rv-sage` | `#6b8c5a` | Primary — sage green |
| `--rv-sage-dark` | `#4a6340` | Hover |
| `--rv-mushroom` | `#8a7060` | Warm mushroom brown — secondary accent |
| `--rv-sea` | `#4a7c8a` | Sea-vegetable teal — used sparingly |
| `--rv-turmeric` | `#d4a020` | Ayurvedic gold — used sparingly |
| `--rv-text-1`–`--rv-text-4` | `#1e2a1e` → `#8a9c7c` | Forest → muted ramp |
| `--rv-text-inv` | `#f2f5ee` | Text on dark |
| `--rv-border` | `rgba(60,80,40,0.14)` | Subtle dividers |

For the *Collective's* Ridge & Valley vendor card, only `--rv-sage` (`#6b8c5a`) crosses over.

### Contrast targets (verify in browser)

- `--cc-text-1` on `--cc-bg` — body text, very high contrast, fine
- `--cc-green` on `--cc-bg` — used for primary buttons (white text on green) and inline emphasis; ratio ≈ 6:1 — safe for body links if underlined
- `--cc-ochre` on `--cc-bg` — eyebrow labels at 11px / 600 weight; ratio ≈ 3.6:1 — *only* at large sizes or used as a non-text accent (divider bar, icon). Don't put body links in ochre.
- `--cc-text-inv` on `--cc-bg-dark` — footer text, fine

No dark mode in v1. The Collective surface is designed for cream.

---

## Typography

Three faces, one per brand. Self-host once chosen.

### Collective — Fraunces + Work Sans

Decided over the design handoff's Lora + DM Sans suggestion. Fraunces is a variable serif with a `SOFT` axis we push toward warm/rounded — it gives the Collective umbrella a distinctive editorial-but-warm voice that doesn't echo Starving Dragon's Playfair Display. Work Sans is a humanist sans with personality without going corporate.

```scss
:root {
  --cc-font-display: "Fraunces", Georgia, "Times New Roman", serif;
  --cc-font-body:    "Work Sans", -apple-system, system-ui, sans-serif;
}
```

Google Fonts import for Collective pages:
```html
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght,SOFT@0,9..144,400..700,30..100;1,9..144,400..600,30..100&family=Work+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
```

Heading style: Fraunces, weight 500–600, `SOFT` pushed high (≥80), sentence case, `-0.01em` to `-0.02em` letter-spacing on display sizes.

### Starving Dragon — Playfair Display + Inter

Their existing pairing. Keep verbatim.

```scss
:root {
  --sd-font-display: "Playfair Display", Georgia, "Times New Roman", serif;
  --sd-font-body:    "Inter", system-ui, -apple-system, sans-serif;
}
```

### Ridge & Valley — TBD

No font decision until R&V validates direction. Working hypothesis: a softer transitional serif (e.g., Cormorant, Crimson Pro, EB Garamond) + a humanist sans (e.g., Nunito Sans, Source Sans, Public Sans). Don't pick before vendor input.

### Type scale (Collective)

Base 18px, 1.25 modular ratio.

| Token | Px | rem | Use |
| --- | --- | --- | --- |
| `--cc-fs-eyebrow` | 11px | 0.6875 | Uppercase eyebrow labels |
| `--cc-fs-xs` | 14px | 0.875 | Captions, footer |
| `--cc-fs-sm` | 16px | 1.0 | Secondary body |
| `--cc-fs-md` | 18px | 1.125 | Body default |
| `--cc-fs-lg` | 22px | 1.375 | Lede, vendor card titles |
| `--cc-fs-xl` | 28px | 1.75 | Section headings |
| `--cc-fs-2xl` | 36px | 2.25 | Page titles |
| `--cc-fs-3xl` | 48px | 3.0 | Hero (mobile) |
| `--cc-fs-4xl` | 64px | 4.0 | Hero (desktop) |

Line heights: 1.6 body, 1.2 display, 1.35 between.

Eyebrow label spec: `--cc-fs-eyebrow`, weight 600, `letter-spacing: 0.18em`–`0.22em`, uppercase, color `--cc-ochre`. Pairs with the divider bar (below).

---

## Spacing

4px base, geometric.

| Token | Px |
| --- | --- |
| `--space-1` | 4 |
| `--space-2` | 8 |
| `--space-3` | 12 |
| `--space-4` | 16 |
| `--space-5` | 20 |
| `--space-6` | 24 |
| `--space-8` | 32 |
| `--space-10` | 40 |
| `--space-12` | 48 |
| `--space-16` | 64 |
| `--space-20` | 80 |
| `--space-24` | 96 |

Section vertical rhythm: `--space-20` to `--space-24` between major sections on desktop, `--space-16` on mobile.

## Layout

- Max content width: **72ch** for prose, **960–1100px** for layouts with cards
- Single content column by default; two columns only when content benefits (vendor card grid)
- Generous side padding on mobile: `--space-5` minimum (`--space-6` preferred)
- Don't center body text. Left-align prose. Center is reserved for hero, About section.

## Borders, radii, shadows

- **Border:** 1px solid `--cc-border` for subtle dividers, 1px `--cc-border-mid` for card/nav borders
- **Radius:** small only. `--radius-sharp: 2px` (Starving Dragon style), `--radius-sm: 4px`, `--radius-md: 6px` (Collective default). No pills, no rounded heroes.
- **Shadows:** sparingly. Tokens:
  - `--cc-shadow-sm: 0 1px 4px rgba(30,20,10,0.08)`
  - `--cc-shadow-md: 0 4px 16px rgba(30,20,10,0.10)` — vendor card resting state
  - `--cc-shadow-lg: 0 8px 32px rgba(30,20,10,0.12)` — vendor card hover

The look is closer to a printed market poster than a SaaS dashboard.

---

## Components

These come from the design handoff and are the canonical patterns for the Collective. Implement as Liquid includes once Jekyll is bootstrapped.

### Section eyebrow + title + divider

The Collective's repeating section anchor:
```
[Eyebrow label]   <-- --cc-fs-eyebrow, --cc-ochre, uppercase, 0.22em tracking
[Section title]   <-- Fraunces, --cc-fs-xl or --cc-fs-2xl, --cc-text-1
[Divider bar]     <-- 40px × 2px, --cc-ochre, margin below
```

Centered on About sections (with the divider also centered); left-aligned everywhere else.

### Hero

- Background: solid `--cc-bg` with two radial gradient glows layered behind:
  - `radial-gradient(ellipse at 60% 30%, rgba(90,138,74,0.10) 0%, transparent 55%)` — green
  - `radial-gradient(ellipse at 30% 70%, rgba(196,131,26,0.08) 0%, transparent 50%)` — ochre
- Eyebrow → headline (Fraunces, `--cc-fs-3xl`/`--cc-fs-4xl`, 500–700) → italic subhead (Fraunces italic, `--cc-fs-md`) → one-paragraph desc (`--cc-fs-md`, `--cc-text-3`) → CTA row
- Italic emphasis inside the headline can take `--cc-green` to subtly tint the bridge word (e.g., "Local makers. *Real flavor.*"). Use once per page max.
- One primary + one ghost CTA. No carousel.

### Buttons

```
.btn-primary
  background: --cc-green; color: --cc-text-inv;
  padding: 14px 32px; border-radius: --radius-md;
  font: 600 13px/1 --cc-font-body; letter-spacing: 0.07em; text-transform: uppercase;
  hover: background --cc-green-light; transform: translateY(-1px);

.btn-outline
  background: transparent; color: --cc-text-2;
  border: 1.5px solid --cc-border-mid; padding: 13px 30px (1px less to match height);
  same typography rules as primary;
  hover: border-color --cc-green; color --cc-green;
```

No icon-only buttons unless icon is universally recognized.

### Vendor card (typographic)

No image required for v1 — use this card pattern. Image-first variant comes back in Phase 2.

```
[Top border accent — 3px, vendor color]   <-- --sd-accent for SD, --rv-sage for R&V
[Category badge — pill]                    <-- vendor-color background at ~10% alpha
[Vendor name — Fraunces, --cc-fs-lg]
[Tagline — Fraunces italic, --cc-fs-sm, --cc-text-4]
[Description — Work Sans, --cc-fs-sm, --cc-text-3]
[Tag chips — Work Sans, 11px, --cc-text-4 on --cc-bg-section]
[Action link — uppercase, vendor color, → arrow]
```

- Card background: `--cc-bg-card`
- Border: 1px `--cc-border` + the 3px top accent
- Padding: `--space-8` (32) on mobile, `--space-9 --space-8` on desktop
- Hover: lift via `--cc-shadow-lg`, `translateY(-2px)`
- Whole card behaves as a focusable region; primary action is the link at the bottom

### Stat / pickup-info card

From Starving Dragon, generalized:
```
[Eyebrow label — uppercase ochre, 0.18em]
[Value — mono or display]
```
Border-left: 2px solid accent, padding-left: 24px. No background, no shadow. Used for pickup times, addresses, "made in batch of X."

### Disclosure block (TN cottage food)

Required on individual vendor pages.
- Background: `--cc-bg-section`
- Text: `--cc-text-3`, `--cc-fs-sm`
- Padding: `--space-4`
- Optional: small line-icon (home, leaf) on the left
- Confirm exact wording with each vendor — TN statute language varies by category

### Values grid (3-up)

From the design handoff. 3 columns desktop, stacked mobile, 1px gap on `rgba(60,40,10,0.10)` background creates the inset dividers between cells.

- **Icons:** swap the design handoff's emoji (🌿🏡✦) for **Lucide line icons** (`leaf`, `home`, `users` — 24px, 1.5px stroke, color `--cc-ochre`). The ✦ is fine as a decorative separator elsewhere; for the values grid, line icons read cleaner.
- Each card: icon → `<h3>` (Fraunces, `--cc-fs-md`–`lg`) → 1–2 sentence body (`--cc-fs-sm`)

### Footer

Dark wood (`--cc-bg-dark`), 3 columns + copyright row.
- Logo + brand name + "Chattanooga, TN · Cottage Food" sub
- "Vendors" column (links to each vendor page)
- "Collective" column (About, Find Us, Join the Collective)
- Copyright + "Tennessee Cottage Food Law compliant"

---

## Iconography

- **Lucide** for the Collective and Ridge & Valley pages — line, 1.5px stroke, sized to match adjacent text
- Starving Dragon's existing custom Instagram SVG matches the Lucide style; keep it
- No filled emoji-style icons; no FontAwesome cottage clip art
- Decorative: `✦` is allowed as a separator (dot · is also fine). No 🌿🏡 in production.

## Imagery

Defined in `docs/brand-guidelines.md` — anti-stock, daylight, hands-in-frame. Add here:

- Default treatment: slight desaturation (~10%) so vendor photos sit in the same color world. Hover removes desaturation.
- Aspect ratios: 4:3 for cards, 21:9 for hero, 1:1 for tight grids
- Empty image slot: `--cc-bg-section` block with a single line of `--cc-text-4` text "Photo coming soon" — never a stock placeholder

## Motion

Almost none.

- Hover transitions: 150–200ms ease-out, color/opacity/transform only
- `translateY(-1px)` for button hover, `translateY(-2px)` for vendor card hover — that's the entire motion budget
- No scroll-triggered animations, no fade-ins, no parallax
- Respect `prefers-reduced-motion: reduce`

## Accessibility

- WCAG **AA** minimum on every shipped route; AAA where easy
- Body text minimum 18px (in the scale)
- Never rely on color alone — links are underlined, not just colored
- Focus ring: `2px solid --cc-ochre`, `2px` offset
- Alt text required: vendor name + what's in the photo. `alt=""` only for purely decorative images.

---

## CSS variable manifest (drop-in starter)

When the SCSS comes in, this is the `:root` block. Tokens are namespaced by brand so vendor pages can scope without leaking.

```scss
:root {
  /* ── Chattanooga Collective ─────────────────────── */
  --cc-bg:          #f5f0e8;
  --cc-bg-section: #ede6d8;
  --cc-bg-card:    #faf7f2;
  --cc-bg-dark:    #2a2018;

  --cc-text-1:   #1e1a14;
  --cc-text-2:   #3d3020;
  --cc-text-3:   #6a5438;
  --cc-text-4:   #9a7d58;
  --cc-text-5:   #bda882;
  --cc-text-inv: #f5f0e8;

  --cc-green:        #3a5c3a;
  --cc-green-light:  #5a8a4a;
  --cc-ochre:        #c4831a;
  --cc-ochre-light:  #e8a83a;
  --cc-rust:         #a04520;
  --cc-rust-light:   #c86040;

  --cc-border:        rgba(60,40,10,0.12);
  --cc-border-mid:    rgba(60,40,10,0.22);
  --cc-border-accent: rgba(164,100,32,0.30);

  --cc-shadow-sm: 0 1px 4px rgba(30,20,10,0.08);
  --cc-shadow-md: 0 4px 16px rgba(30,20,10,0.10);
  --cc-shadow-lg: 0 8px 32px rgba(30,20,10,0.12);

  --cc-font-display: "Fraunces", Georgia, serif;
  --cc-font-body:    "Work Sans", -apple-system, system-ui, sans-serif;

  --cc-fs-eyebrow: 0.6875rem; /* 11px */
  --cc-fs-xs:  0.875rem;
  --cc-fs-sm:  1rem;
  --cc-fs-md:  1.125rem;
  --cc-fs-lg:  1.375rem;
  --cc-fs-xl:  1.75rem;
  --cc-fs-2xl: 2.25rem;
  --cc-fs-3xl: 3rem;
  --cc-fs-4xl: 4rem;

  /* ── Starving Dragon ────────────────────────────── */
  --sd-bg:          #0d0703;
  --sd-bg-section:  #110904;
  --sd-bg-footer:   #080402;
  --sd-accent:      #e8522a;
  --sd-accent-dark: #c43d1a;
  --sd-accent-glow: rgba(200,60,10,0.20);
  --sd-text-1: #f5ede0;
  --sd-text-2: #c4aa8a;
  --sd-text-3: #b89870;
  --sd-text-4: #a88858;
  --sd-text-5: #987848;
  --sd-text-6: #886838;
  --sd-text-7: #705028;
  --sd-border:       rgba(200,80,20,0.12);
  --sd-border-mid:   rgba(200,80,20,0.20);
  --sd-border-hover: rgba(232,82,42,0.40);
  --sd-font-display: "Playfair Display", Georgia, serif;
  --sd-font-body:    "Inter", system-ui, -apple-system, sans-serif;

  /* ── Ridge & Valley ─────────────────────────────── */
  --rv-bg:         #f2f5ee;
  --rv-bg-section: #e4ebe0;
  --rv-bg-dark:    #1e2a1e;
  --rv-bg-card:    #ffffff;
  --rv-sage:        #6b8c5a;
  --rv-sage-dark:   #4a6340;
  --rv-mushroom:    #8a7060;
  --rv-sea:         #4a7c8a;
  --rv-turmeric:    #d4a020;
  --rv-text-1: #1e2a1e;
  --rv-text-2: #3a4e30;
  --rv-text-3: #5c6e50;
  --rv-text-4: #8a9c7c;
  --rv-text-inv: #f2f5ee;
  --rv-border: rgba(60,80,40,0.14);
  /* fonts: TBD */

  /* ── Shared ─────────────────────────────────────── */
  --space-1:  0.25rem;
  --space-2:  0.5rem;
  --space-3:  0.75rem;
  --space-4:  1rem;
  --space-5:  1.25rem;
  --space-6:  1.5rem;
  --space-8:  2rem;
  --space-10: 2.5rem;
  --space-12: 3rem;
  --space-16: 4rem;
  --space-20: 5rem;
  --space-24: 6rem;

  --radius-sharp: 2px;
  --radius-sm:    4px;
  --radius-md:    6px;
}
```

## Open questions

- Final wordmark for Collective — does it want a mark, or wordmark-only? (Starving Dragon's vintage badge is the comparison point; the Collective should look quieter, not louder.)
- Ridge & Valley type pairing — pick once vendor signs off
- Whether to introduce a "member of Chattanooga Collective" badge component for vendors to embed on their own external sites
- Whether the homepage hero earns a real photo over the radial-gradient cream surface — only once we have one we like
