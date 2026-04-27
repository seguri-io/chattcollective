# Roadmap

Phased, dateless. Each phase has a clear "done" condition; no phase starts until the prior one's done condition is true. The point is to ship something honest and small, then expand only where there's real demand from vendors or readers.

Anchored to:
- `docs/brand-guidelines.md` — voice, audience, what we are/aren't
- `docs/design-system.md` — palette, type, components
- `CLAUDE.md` — architecture conventions

---

## Phase 0 — Foundations

**Done when:** the docs that drive every later decision exist and have been read by the active vendors.

- [x] `CLAUDE.md`
- [x] `docs/brand-guidelines.md` — reflects three-brand structure (Collective + Starving Dragon + Ridge & Valley)
- [x] `docs/design-system.md` — three-palette token structure, components reconciled against the Claude Design handoff
- [x] `ROADMAP.md` (this file)
- [x] Starving Dragon logo received and stored at `assets/images/vendors/starving-dragon/logo.png`
- [x] Original design handoff preserved at `docs/handoff/` for reference
- [ ] **Collective wordmark** — needs design exploration via claude.ai design surface; quieter than Starving Dragon's vintage badge so it can sit above both vendors without competing
- [ ] **Ridge & Valley visual identity** — proposed in the design system as `--rv-*` tokens (sage/mushroom/sea/turmeric, fonts TBD); needs vendor sign-off before going live anywhere
- [ ] Both vendors read the brand & design docs and push back on anything that doesn't fit — especially the inferred Ridge & Valley voice and the proposed R&V palette

## Phase 1 — MVP launch

**Goal:** a Chattanooga local can find both vendors and reach them. Nothing more.

**Done when:** `chattcollective.com` resolves to a site that passes the launch checklist below, and both current vendors have approved their profile copy.

Site scope:
- [ ] Jekyll bootstrap (`_config.yml`, `Gemfile.lock` excluded, base SCSS using design system tokens, Minimal Mistakes remote theme — drop the theme if any design decision can't be expressed via override)
- [ ] Layouts: home, vendor, page (about/contact)
- [ ] Components implemented per design system: section eyebrow + title + divider, hero (radial-gradient cream, no photo), typographic vendor card (badge + name + tagline + desc + tag chips + accent top-border in vendor color), button (primary + ghost), disclosure block, stat/pickup card, values 3-up
- [ ] Homepage — hero (radial-gradient cream surface, no photo for v1), one-paragraph intro, two vendor cards, values 3-up, find-us section, footer per design handoff
- [ ] `/vendors/` index — same two cards, room for more
- [ ] `/vendors/ridge-and-valley/` — vendor blurb (Appalachian-rooted framing, validated with vendor), what they make in plain language, pickup block, contact link, TN cottage food disclosure. No photo required for v1; vendor-color accent stripe is `--rv-sage`
- [ ] `/vendors/starving-dragon/` — same shape; vendor's own copy ("craft-batch," "Spewing heat since 2026" etc. preserved verbatim); accent stripe is `--sd-accent`; outbound link to starvingdragon.com opens new tab with `rel="noopener"`
- [ ] `/about/` — the collective's origin and how it works (directory, not storefront)
- [ ] `/contact/` — general collective inquiries; per-vendor contact stays on vendor pages
- [ ] `404.md`
- [ ] `jekyll-seo-tag` configured with default OG image and per-page overrides
- [ ] `sitemap.xml` and `feed.xml` (jekyll-feed only if/when a blog exists — skip otherwise)
- [ ] Custom domain wired (`CNAME` file + DNS), HTTPS enforced
- [ ] Favicon set generated from final wordmark

Quality bars before launch:
- [ ] Lighthouse a11y ≥ 95 on every shipped route
- [ ] Color contrasts verified against design system table
- [ ] All images have meaningful `alt` text (vendor + subject), or are explicitly decorative
- [ ] Cottage food disclosure language confirmed with each vendor — exact wording, not boilerplate
- [ ] Tested on a real phone in real daylight (it's a food site; that's where it'll be read)
- [ ] No third-party tracking, no analytics — defer that decision

Explicitly out of scope for Phase 1: products collection, blog, online ordering, newsletter.

## Phase 2 — Content depth & visual polish

**Goal:** the site stops feeling like a stub.

**Done when:** every vendor profile has real photography, the wordmark is integrated, and the homepage has a tagline the vendors are happy with.

- [ ] Real photography sweep — daylight, hands-in-frame, anti-stock; replace any "Photo coming soon" placeholders
- [ ] Wordmark / logo integrated into masthead and favicon
- [ ] Final tagline picked from brand guide candidates (or new one), wired into hero + meta description
- [ ] Per-vendor "what we make" list — short bullet list, not a catalog (catalogs come later if at all)
- [ ] Pickup/availability blocks live on each vendor page with mono-numerics styling per design system
- [ ] Vendor profiles expanded — longer first-person copy from the vendor, multiple photos, links to their own social/site
- [ ] Image optimization: `.webp` with sensible widths, `loading="lazy"`, `<picture>` where appropriate
- [ ] Self-host fonts (subsetted) under `assets/fonts/`
- [ ] Performance budget set and verified (target: ≤ 75KB CSS, ≤ 200KB images on homepage above-the-fold, no JS unless required)

## Phase 3 — Products collection (gated on demand)

**Goal:** surface specific things across vendors so a reader looking for "sourdough" or "hot honey" finds it without having to read each vendor page.

**Gate:** don't start this until at least 4 vendors are live OR readers/vendors specifically ask for it. With 2 vendors, vendor pages do this job better than a products index.

- [ ] `_products/` collection wired up per `CLAUDE.md` architecture
- [ ] One product file per *category a vendor offers* (not one per SKU — we're not a store)
- [ ] Products index with category filter
- [ ] Bidirectional links: vendor pages list their products, product pages list contributing vendors
- [ ] Decide whether prices appear here. Default: no, because they change and we're not selling.

## Phase 4 — Onboarding & growth

**Goal:** new cottage food makers in Chattanooga can find the collective and apply to join without a pre-existing relationship.

**Done when:** at least one new vendor has come through the published onboarding path.

- [ ] `/join/` page — what the collective is, what membership requires, what it doesn't (it's not a co-op, no shared kitchen, no fees if that stays true)
- [ ] Lightweight application — email-based, no form-builders
- [ ] Internal `docs/vendor-onboarding.md` — checklist for adding a new vendor: photos, blurb, contact, disclosure language confirmation, profile review
- [ ] Optional: a "members" badge / link snippet vendors can put on their own sites (open question in design system — resolve before building)

## Maybe-never (deliberately deferred)

These have been considered and intentionally aren't on the roadmap. They go here so we don't accidentally drift into them and so future contributors see the prior thinking.

- **E-commerce / online ordering** — TN cottage food law has narrow boundaries; the brand premise is buy direct from the maker. Re-open only if the legal landscape changes or a vendor explicitly wants it.
- **Out-of-state shipping** — same reason.
- **Blog / journal** — fine in principle, but only if a vendor or the collective actually wants to write. Don't add the machinery speculatively.
- **Events calendar** — only if the collective ever does pop-ups together. One-off events can live in a vendor's own page.
- **Newsletter** — minimal-tool only (e.g., Buttondown) and only if there's a clear reason someone would want one. No marketing automation.
- **JS framework / build pipeline** — the site shouldn't need it. If a feature seems to require one, that's a flag to question the feature.

## Cross-cutting concerns

These don't belong to a single phase; check them every phase.

- **Legal review checkpoint** — before any vendor profile goes live or changes, confirm cottage food disclosure language with the vendor (not boilerplate)
- **Voice review** — every new piece of collective-wide copy gets read against brand guide do/don't list before merge
- **A11y audit** — before each phase ships, run an automated check + a manual keyboard pass
- **Performance budget** — set in Phase 2, enforced afterward; CI check is overkill for now, manual is fine
- **Vendor consent** — the site represents real people. Vendor-specific changes get their explicit OK before going live.
