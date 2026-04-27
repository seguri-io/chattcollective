# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

**Chattanooga Collective** is the marketing site for a devoted group of artisan cottage food makers in Chattanooga, TN. It's a static GitHub Pages / Jekyll site at `chattcollective.com` (the URL is the contraction; the public name is "Chattanooga Collective" — don't use "Chatt Collective" in headlines or formal copy). The site's job is to (a) help locals find homemade goods from members and (b) give each member a section they can link out to. Members operate under Tennessee's Domestic Kitchen / cottage food rules — the site does not handle payments or fulfillment.

This is **three brands, not one**: the Collective umbrella plus member sub-brands. The design system has separate token sets (`--cc-*`, `--sd-*`, `--rv-*`) so member accents can sit on the Collective surface without flattening any member's identity.

The site is **single-page**: every section lives on the homepage; nav links are anchor jumps. The only standalone files are the homepage (`index.html`) and the 404 page. Member content lives in a `_members/` Liquid collection with `output: false` — the homepage iterates and renders each member as a full-width panel inline.

Current members:
- **Starving Dragon** — Sichuan chili crisp oil, craft-batch. Has its own existing brand (dark/moody site, vintage illustrated badge logo, Playfair Display + Inter, chili-red `#e8522a`). Site: https://starvingdragon.com. Tagline: "Spewing heat since 2026."
- **Ridge & Valley** — functional allergen-free foods (sea vegetables, adaptogenic mushrooms, ayurvedic spices) with an Appalachian-rooted framing (the name comes from the Ridge and Valley Appalachians). No site yet; visual identity is proposed pending member sign-off.

## Source of truth for visual & voice decisions

Before changing site copy, layout, color, or typography, read:

- `docs/brand-guidelines.md` — mission, three-brand structure, voice rules per brand, name treatment, photography direction
- `docs/design-system.md` — palette tokens (three brands), typography, spacing, component patterns
- `ROADMAP.md` — what phase the site is in and what's intentionally not built yet
- `docs/handoff/` — the original Claude Design handoff bundle, preserved as reference. The brand and design docs above are authoritative; the handoff is for context only.

If a decision isn't covered there, surface that gap rather than inventing one inline. Update the doc, then implement.

**Voice rules that catch everyone out:**
1. The "no marketing-speak" list (no "curated," "experience," "journey," "passionate") applies to *Collective-authored* copy only. Each member's voice is sovereign — Starving Dragon literally calls itself "craft-batch," and that's their identity to keep. When the Collective introduces a member, quote them or use their own framing; don't paraphrase into Collective voice.
2. The Collective brand voice is **plainspoken neighbor with Appalachian collectivity** — neighbors helping neighbors as a real regional habit, not a marketing convenience. Lean into that ethos.
3. The participants are **members**. Never "vendors," "partners," "creators," or "brands."
4. **No specific counts** in copy ("two members," "small group of"). Leave room for growth — use "multiple makers," "our members," "the Collective."
5. **Don't say "front door"** as a metaphor. Use plain language: "shared website" or describe what the Collective actually does.

## Tennessee cottage food context

Members sell under Tennessee's Domestic Kitchen / Tennessee Food Freedom Act rules. This shapes what the site can and can't claim:

- Member panels should not imply commercial-kitchen production unless the member actually has one
- Required disclosures (e.g., "made in a home kitchen not subject to inspection by the Tennessee Department of Agriculture") belong on individual member panels, not buried in a footer — confirm wording with each member
- Don't add e-commerce, shipping, or interstate sales features without checking with members first; the legal envelope is narrower than typical online retail

When in doubt, leave a `TODO(legal)` comment and ask rather than guessing.

## Commands

Local development uses standard Jekyll + Bundler. Run from the repo root:

```bash
bundle install                                  # first time, or after Gemfile changes
bundle exec jekyll serve --livereload           # http://127.0.0.1:4000 with auto-reload
bundle exec jekyll build                        # one-shot build into _site/
bundle exec jekyll doctor                       # config / URL sanity check
```

There is no test suite, linter, or formatter wired up yet. Don't fabricate one — if you want to add one (e.g., `htmlproofer`, `prettier` for SCSS), discuss it first.

GitHub Pages builds on push to `main`; no separate deploy step.

## Architecture

The site is intentionally small. Custom Jekyll, no theme.

- **Theme:** None. We tried Minimal Mistakes provisionally and dropped it — the design system is opinionated enough that overriding the theme was more work than writing custom layouts.
- **Layouts:** `_layouts/default.html` (shell with nav + footer + head) and `_layouts/home.html` (no-op passthrough that wraps the homepage in default — kept as a hook for future hero-specific styling).
- **Includes:** `head`, `nav`, `footer`, `section_header`, `member` (renders one member's full panel), `disclosure` (TN cottage food block, used inside each member panel).
- **Collections:** `_members/` with `output: false`. One Markdown file per member; the homepage iterates and renders inline. Don't reintroduce per-member output unless there's a real reason — the single-page architecture has been a deliberate choice.
- **Data:** `_data/navigation.yml` — main nav. Anchor links into the homepage (`/#members`, `/#why`, `/#find`).
- **Pages:** there is no `_pages/` directory. About / Contact / Members were standalone pages in an earlier draft and were folded into the homepage.
- **Posts:** `_posts/` only if/when a blog is in scope per the roadmap. Don't add it speculatively.
- **Assets:** `assets/images/vendors/<slug>/` for member photography and logos (e.g. `assets/images/vendors/starving-dragon/logo.png` is the real member-supplied badge). The folder is named `vendors` for consistency with how the Starving Dragon logo asset was originally received — leave the folder name even though we say "members" in copy. Prefer `.webp` with `.jpg` fallback only if a specific browser issue forces it.

## Deploy / preview

The site is currently previewed at `https://seguri-io.github.io/chattcollective/`. To make this work at the github.io subpath, `_config.yml` includes a temporary `baseurl: /chattcollective`. When the custom domain `chattcollective.com` is wired (Settings → Pages → Custom domain), **remove that baseurl line** so the site moves to the apex.

All internal links use Liquid's `relative_url` filter, so the `baseurl` swap is the only change needed.

## Conventions

- New member → new file in `_members/<slug>.md` with the front-matter shape used by `_includes/member.html` (title, order, accent, category, tagline, summary, tags, external_url or coming_soon).
- Member copy is the member's own — do not rewrite it for "tone" without confirmation. Voice guidelines apply to Collective-wide copy.
- External links to a member's own site (e.g., Starving Dragon) open in a new tab with `rel="noopener"`.
- Keep root-level Markdown limited to project meta (`README.md`, `CLAUDE.md`, `ROADMAP.md`). Site content lives in collections or `index.html`.

## Things not to do

- Don't add Jekyll plugins outside the [GitHub Pages allowlist](https://pages.github.com/versions/) — the build will silently fall back and behaviors diverge
- Don't introduce JS frameworks, bundlers, or Node tooling for what plain Liquid + SCSS can handle
- Don't add tracking, analytics, or third-party embeds without confirming — this is a small community-facing site
- Don't reintroduce a multi-page architecture without a real reason. The single-page version was chosen deliberately.
- Don't commit `Gemfile.lock`, `_site/`, or `.jekyll-cache/` (already in `.gitignore`)
