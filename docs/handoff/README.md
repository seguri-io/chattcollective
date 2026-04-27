# Chattanooga Collective — Design System

## Overview

**Chattanooga Collective** is a local cottage food vendor collective based in Chattanooga, TN. It serves as an umbrella brand uniting independent cottage food makers, giving them shared marketing presence and a collective website while each member retains their own identity.

**Current members (2):**
| Member | Product Focus | Vibe |
|---|---|---|
| **Starving Dragon** | Sichuan chili crisp oil, craft-batch | Dark, bold, fire/heat aesthetic |
| **Ridge and Valley** | Functional allergen-free foods (sea vegetables, functional mushrooms, ayurvedic spices) | Earthy, nourishing, apothecary/wellness |

The Collective itself is a **new brand to be created** — it serves as the front door to both vendors on a shared website.

---

## Source Materials

| Source | URL / Path | Status |
|---|---|---|
| Starving Dragon website | https://starvingdragon.com/ | Down at time of build |
| Starving Dragon GitHub | https://github.com/tritzriley/starvingdragon/blob/main/index.html | ✅ Read |
| Starving Dragon Instagram | https://www.instagram.com/starvingdragonoil/ | Not fetched (auth wall) |
| Ridge and Valley | No URL yet | ⚠️ Not launched |
| Collective brand | None | 🆕 Created here |

> **Logo:** `assets/starving-dragon-logo.png` — Real logo provided by vendor. Illustrated vintage badge style: cartoon dragon breathing fire and eating chilies, circular format with arched "STARVING DRAGON" type, ribbon banner reading "CHILI CRISP OIL · SPEWING HEAT SINCE 2026", and humorous "OM NOM / NOM" speech bubbles. Works on both dark and parchment backgrounds.

---

## Brand Members

### Starving Dragon
- **Product:** Sichuan chili crisp oil, craft-batch, Chattanooga TN
- **Tagline:** "Spewing heat since 2026"
- **Aesthetic:** Dark, moody, sophisticated heat. Deep near-black backgrounds, burnt-orange/chili-red accent, warm cream type, Playfair Display serif + Inter sans.
- **Website:** Single-page HTML at the GitHub repo above.

### Ridge and Valley
- **Product:** Functional foods — allergen-free with superfoods (sea vegetables, functional mushrooms, ayurvedic spices). Focus on foods that taste as good or better than conventional alternatives.
- **Aesthetic:** To be defined. Suggested direction: earthy apothecary, botanical, warm forest greens and ochre.
- **Website:** Not yet launched.

### Chattanooga Collective (umbrella)
- **Purpose:** Shared website / marketing hub for both vendors
- **Aesthetic:** Earthy & rustic — natural textures, warm tones, handwritten-style type. Bridges the bold heat of Starving Dragon with the nourishing wellness of Ridge and Valley.

---

## CONTENT FUNDAMENTALS

### Voice & Tone
**Starving Dragon:**
- Bold and confident. Unabashedly spicy.
- Short, punchy phrases: "Spewing heat since 2026", "Craft-batch · Chattanooga, TN"
- Uses the word "craft" deliberately — artisan, not mass-produced.
- Sichuan vocabulary used without being precious about it (chili crisp, numbing heat).
- Third person product descriptions, second person CTAs ("Order yours").
- No emoji in UI text; emoji used sparingly in pairing cards as decoration only.
- All-lowercase section labels feel editorial; proper title case for headings.
- Copy is written for adults who like food and know spice. Not dumbed down.

**Ridge and Valley (inferred):**
- Warm and educational — ingredients deserve explanation.
- Functional/wellness vocabulary: superfoods, adaptogens, allergen-free, nourishing.
- Inclusive and welcoming: "taste just as good or better" — not preachy.
- Likely uses "you" (second person) — personal and direct.

**Chattanooga Collective:**
- Community-first. "Local" and "together" are core concepts.
- Celebrates craft and place (Chattanooga, TN is an identity marker).
- Warm but not folksy. Approachable but not cutesy.
- Casing: Title Case for product names, lowercase for descriptors.
- No excessive emoji. Maybe a single ✦ or · as a decorative separator.

---

## VISUAL FOUNDATIONS

### Color System
See `colors_and_type.css` for all CSS variables.

**Starving Dragon palette:**
- Near-black backgrounds (`#0d0703`, `#110904`, `#080402`)
- Chili red/orange accent: `#e8522a`
- Warm cream text: `#f5ede0` → `#c4aa8a` → `#b89870` → `#a88858` → `#987848` → `#886838` → `#705028` (darkening ramp)
- Borders: `rgba(200,80,20,0.12)` — very subtle warm-tinted lines

**Collective palette (designed):**
- Forest floor greens, warm ochre, kraft/cream backgrounds
- See `colors_and_type.css` for full token set

### Typography
**Starving Dragon:**
- Display: **Playfair Display** (Google Fonts) — weights 700, 900; italic 400, 700
- Body: **Inter** (Google Fonts) — weights 300, 400, 500, 600
- H1: clamp(52px–88px), weight 900, line-height 1, letter-spacing -0.02em
- Section title: clamp(28px–44px), weight 900, line-height 1.1
- Italic hero subtitle: clamp(18px–24px), Playfair italic
- Eyebrow labels: 11px, uppercase, 0.22em letter-spacing, weight 600, color accent
- Body copy: 15–17px, line-height 1.8, warm muted colors
- Nav links: 12px, uppercase, 0.1em letter-spacing, weight 500

**Collective:**
- Display: **Lora** (Google Fonts) — elegant, friendly serif. Substitution note: similar feel to a hand-set editorial serif.
- Body: **DM Sans** (Google Fonts) — clean, modern, slightly geometric.

### Backgrounds
- Starving Dragon: Flat dark `#0d0703` with radial gradient glows in key hero areas (chili glow from bottom center). No photography visible in code — likely product photos not yet added.
- Collective: Warm kraft-paper cream `#f5f0e8`. Could layer subtle paper textures via CSS noise or real texture images.

### Animation & Interaction
- **Starving Dragon:** Minimal. Color transitions at 0.2s ease. Button hover: `translateY(-1px)` + darker color at 0.15s. No scroll animations coded.
- **Collective (recommended):** Subtle fade-in on scroll. No bouncy animations — keep grounded and artisan.

### Borders & Radius
- Starving Dragon: `border-radius: 2px` only — nearly sharp corners. Thin 1px borders.
- Collective: Allow up to 4–6px radius for a friendlier feel. Still not fully rounded.

### Cards
- Starving Dragon: Grid cards use `1px` gap with `rgba(200,80,20,0.12)` background-color acting as border between cells. Inner cells are flat `#0d0703`. No shadow.
- Stat cards: `border-left: 2px solid #e8522a; padding-left: 24px` — no box shadow.

### Dividers
- Starving Dragon: `44px × 2px`, solid `#e8522a` — used below section labels.

### Iconography
See ICONOGRAPHY section below.

### Logo
**Starving Dragon:** Illustrated vintage badge — a cartoon dragon breathing fire and eating chilies, rendered in a hand-drawn style with a circular badge format. Arched "STARVING DRAGON" type on a dark band at top; ribbon banner at bottom reading "CHILI CRISP OIL · SPEWING HEAT SINCE 2026." Humorous speech bubbles: "OM NOM" and "NOM." The logo is warm, playful, and detailed — it sits in tension with the dark/moody website, giving the brand a dual personality: serious about craft, but not taking itself too seriously. Works cropped to a circle (as used in the hero) or shown full as a badge.

### Imagery vibe
- Starving Dragon: The logo's illustrated warmth (reds, oranges, flame tones, parchment texture in background) implies product photography should be warm-lit and slightly textured — not cold or clinical. Shot against dark backgrounds for the web, but the logo feels great on kraft/parchment too.
- Collective: Natural light. Farmers market feel. Warm, slightly overexposed. Earthy and real.

---

## ICONOGRAPHY

**Starving Dragon:**
- No icon font or SVG sprite system in the codebase.
- One custom SVG icon: Instagram logo (inline SVG, 16×16, stroke-based, stroke-width 1.5). `<rect>` + `<circle>` construction.
- Feature section uses emoji as decorative icons (🌶️ type items in the pairing cards).
- Stat cards and ingredient cards use a 7px circle dot (`•`) as a visual bullet — CSS dot, not an icon font.
- Recommendation for production: Lucide icons (stroke, weight 1.5) match the existing Instagram SVG style perfectly. CDN: `https://unpkg.com/lucide@latest`

**Ridge and Valley:**
- No materials yet. Recommend a botanical/nature icon set — e.g. Phosphor Icons (thin weight) or custom hand-drawn SVGs.

**Collective:**
- Use Lucide for utility icons (nav, arrows, etc).
- Consider a simple hand-drawn-style mark or ampersand as the logo element.

---

## FILES IN THIS DESIGN SYSTEM

```
README.md                          ← This file
SKILL.md                           ← Agent skill manifest
colors_and_type.css                ← All CSS design tokens
assets/
  starving-dragon-logo-placeholder.svg   ← Logo placeholder (need real file)
preview/
  01-sd-colors-dark.html           ← Starving Dragon dark palette
  02-sd-colors-warm.html           ← Starving Dragon warm tones ramp
  03-collective-colors.html        ← Collective brand palette
  04-type-display.html             ← Display type specimens
  05-type-body.html                ← Body + label type specimens
  06-type-scale.html               ← Full type scale
  07-buttons-sd.html               ← Starving Dragon buttons + CTAs
  08-cards-sd.html                 ← Starving Dragon card patterns
  09-nav-sd.html                   ← Starving Dragon navigation
  10-dividers-stats.html           ← Dividers, stat cards, eyebrows
  11-collective-logo.html          ← Collective logo concept
  12-collective-type.html          ← Collective typography
  13-collective-components.html    ← Collective buttons + cards
ui_kits/
  starving-dragon/
    index.html                     ← Interactive Starving Dragon site kit
    README.md                      ← Kit notes
```

---

## CAVEATS & OPEN QUESTIONS

1. **Logo:** The real Starving Dragon logo is embedded in the site as a base64 JPEG — please provide the original file (PNG/SVG) for proper assets.
2. **Ridge and Valley:** No visual materials exist yet. The design system has placeholders for their color palette and typography — these need to be defined with the vendor.
3. **Collective brand:** The colors, logo concept, and typography in this system are a *proposed starting point* — not final. Iterate with stakeholders.
4. **Photography:** No product images are in the repo. The Starving Dragon site likely shows a chili oil bottle — needed for full fidelity mockups.
5. **starvingdragon.com** was down at build time. The GitHub repo is the authoritative source.
