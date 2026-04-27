# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

**Chattanooga Collective** is the marketing site for a small group of independent cottage food vendors in Chattanooga, TN. It's a static GitHub Pages / Jekyll site at `chattcollective.com` (the URL is the contraction; the public name is "Chattanooga Collective" — don't use "Chatt Collective" in headlines or formal copy). The site's job is to (a) help locals find homemade goods from members and (b) give each member a per-vendor profile they can link out to. Members operate under Tennessee's Domestic Kitchen / cottage food rules — the site does not handle payments or fulfillment.

This is **three brands, not one**: the Collective umbrella plus two member sub-brands. The design system has separate token sets (`--cc-*`, `--sd-*`, `--rv-*`) so vendor accents can cross onto Collective pages without flattening either vendor's identity.

Current members:
- **Starving Dragon** — Sichuan chili crisp oil, craft-batch. Has its own existing brand (dark/moody site, vintage illustrated badge logo, Playfair Display + Inter, chili-red `#e8522a`). Site: https://starvingdragon.com. Tagline: "Spewing heat since 2026."
- **Ridge & Valley** — functional allergen-free foods (sea vegetables, adaptogenic mushrooms, ayurvedic spices) with an Appalachian-rooted framing (the name comes from the Ridge and Valley Appalachians). No site yet; visual identity is proposed pending vendor sign-off.

## Source of truth for visual & voice decisions

Before changing site copy, layout, color, or typography, read:

- `docs/brand-guidelines.md` — mission, three-brand structure, voice rules per brand, name treatment, photography direction
- `docs/design-system.md` — palette tokens (three brands), typography, spacing, component patterns
- `ROADMAP.md` — what phase the site is in and what's intentionally not built yet
- `docs/handoff/` — the original Claude Design handoff bundle, preserved as reference. The brand and design docs above are authoritative; the handoff is for context only.

If a decision isn't covered there, surface that gap rather than inventing one inline. Update the doc, then implement.

**Voice rule that catches everyone out:** the "no marketing-speak" list (no "craft," "curated," "artisanal," "experience") applies to *Collective-authored* copy only. Each vendor's voice is sovereign — Starving Dragon literally calls itself "craft-batch," and that's their identity to keep. When the Collective introduces a vendor, quote them or use their own framing; don't paraphrase into Collective voice.

## Tennessee cottage food context

Members sell under Tennessee's Domestic Kitchen / Tennessee Food Freedom Act rules. This shapes what the site can and can't claim:

- Vendor pages should not imply commercial-kitchen production unless the vendor actually has one
- Required disclosures (e.g., "made in a home kitchen not subject to state inspection") belong on individual vendor or product pages, not buried in a footer — confirm wording with the vendor
- Don't add e-commerce, shipping, or interstate sales features without checking with the vendor first; the legal envelope is narrower than typical online retail

When in doubt, leave a `TODO(legal)` comment and ask rather than guessing.

## Commands

Local development uses standard Jekyll + Bundler. Run from the repo root:

```bash
bundle install                                  # first time, or after Gemfile changes
bundle exec jekyll serve --livereload           # http://127.0.0.1:4000 with auto-reload
bundle exec jekyll serve --drafts               # include _drafts/ posts
bundle exec jekyll build                        # one-shot build into _site/
bundle exec jekyll doctor                       # config / URL sanity check
```

There is no test suite, linter, or formatter wired up yet. Don't fabricate one — if you want to add one (e.g., `htmlproofer`, `prettier` for SCSS), discuss it first.

GitHub Pages builds on push to `main`; no separate deploy step.

## Architecture (intended)

Detailed implementation will follow the roadmap, but the shape is:

- **Theme:** Provisionally Minimal Mistakes via `remote_theme`, with project SCSS overrides in `assets/css/main.scss`. The design system has authority — if a documented design decision conflicts with what MM allows via overrides (and forking is the only way), drop the theme rather than fork it. Don't fork.
- **Collections:**
  - `_vendors/` — one Markdown file per member (Ridge & Valley, Starving Dragon, future members)
  - `_products/` — optional later phase, one file per product type
- **Pages:** `_pages/` for top-level pages (about, contact, vendors index, etc.) so root stays clean
- **Data:** `_data/navigation.yml` for the nav, `_data/style.yml` for any tokens that need to be shared between Liquid and SCSS
- **Posts:** `_posts/` only if/when a blog is in scope per the roadmap. Don't add it speculatively.
- **Assets:** `assets/images/vendors/<vendor-slug>/` for vendor photography and logos (e.g. `assets/images/vendors/starving-dragon/logo.png` is the real vendor-supplied badge). Prefer `.webp` with `.jpg` fallback only if a specific browser issue forces it. Source PNGs/SVGs from vendors stay in their original format; lossy re-encode goes through a build step, not a manual conversion.

Liquid front-matter data arrays (à la Minimal Mistakes' `feature_row` pattern) are preferred over hard-coded HTML in pages, so vendors/products can be re-used across views.

## Conventions

- New vendor → new file in `_vendors/<slug>.md` plus an entry referenced from the homepage and vendors index. Don't duplicate vendor copy across files; pull from the collection.
- Vendor copy is the vendor's own — do not rewrite it for "tone" without confirmation. Voice guidelines apply to collective-wide copy.
- External links to a vendor's own site (e.g., Starving Dragon) should open in a new tab and use `rel="noopener"`.
- Keep root-level Markdown limited to project meta (`README.md`, `CLAUDE.md`, `ROADMAP.md`). Site content lives in `_pages/`, collections, or `index.md`.

## Things not to do

- Don't add Jekyll plugins outside the [GitHub Pages allowlist](https://pages.github.com/versions/) — the build will silently fall back and behaviors diverge
- Don't introduce JS frameworks, bundlers, or Node tooling for what plain Liquid + SCSS can handle
- Don't add tracking, analytics, or third-party embeds without confirming — this is a small community-facing site
- Don't commit `Gemfile.lock`, `_site/`, or `.jekyll-cache/` (already in `.gitignore`)
