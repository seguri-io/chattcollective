# Roadmap

Phased, dateless. Each phase has a clear "done" condition; no phase starts until the prior one's done condition is true. The point is to ship something honest and small, then expand only where there's real demand from members or readers.

Anchored to:
- `docs/brand-guidelines.md` — voice, three-brand structure, what we are/aren't
- `docs/design-system.md` — palette tokens (three brands), components
- `CLAUDE.md` — architecture conventions

---

## Phase 0 — Foundations

**Done when:** the docs that drive every later decision exist and have been read by the active members.

- [x] `CLAUDE.md`
- [x] `docs/brand-guidelines.md` — three-brand structure (Collective + Starving Dragon + Ridge & Valley); plainspoken-neighbor voice with Appalachian collectivity ethos
- [x] `docs/design-system.md` — three-palette token structure, components reconciled against the Claude Design handoff
- [x] `ROADMAP.md` (this file)
- [x] Starving Dragon logo received and stored at `assets/images/vendors/starving-dragon/logo.png`
- [x] Original design handoff preserved at `docs/handoff/` for reference
- [ ] **Collective wordmark** — needs design exploration via claude.ai design surface; quieter than Starving Dragon's vintage badge so it can sit above member brands without competing
- [ ] **Ridge & Valley visual identity** — proposed in the design system as `--rv-*` tokens (sage/mushroom/sea/turmeric, fonts TBD); needs member sign-off before going live anywhere
- [ ] Both members read the brand & design docs and push back on anything that doesn't fit — especially the inferred Ridge & Valley voice and the proposed R&V palette

## Phase 1 — MVP launch

**Goal:** a Chattanooga local can find every member, learn what they make, and reach them.

**Done when:** `chattcollective.com` resolves to a site that passes the launch checklist below, and every current member has approved the panel about them.

Architecture: **single-page** site. Every section lives on the homepage; nav links are anchor jumps. The only standalone files are the homepage (`index.html`) and the 404. Members are a Liquid collection (`_members/`) with `output: false` — the Liquid loop renders each member as a full-width panel inline.

Site scope:
- [x] Jekyll bootstrap (no theme; custom layouts and includes; SCSS using design system tokens)
- [x] Layouts: `default`, `home`
- [x] Components implemented per design system: section eyebrow + title + divider, hero (radial-gradient cream surface), member panel (badge + name + tagline + lead + body + tag chips + accent top-border in member color + disclosure), button (primary + ghost), stat/pickup card, market card, values 3-up
- [x] Homepage sections: hero, members (with all panels), why a collective, values, find us
- [x] `_members/starving-dragon.md` — their copy verbatim, accent stripe `--sd-accent`, outbound link to starvingdragon.com (new tab, `rel="noopener"`)
- [x] `_members/ridge-and-valley.md` — Appalachian-rooted draft pending member sign-off, accent stripe `--rv-sage`
- [x] 404 page with branded copy
- [x] `jekyll-seo-tag` configured
- [x] `sitemap.xml` and `feed.xml` (jekyll-feed only outputs feed if posts exist; harmless empty otherwise)
- [x] HTTPS enforced; preview at `https://seguri-io.github.io/chattcollective/`
- [ ] **Voice / copy review by both current members** — every panel and every Collective-authored line read against the brand voice rules
- [ ] **TN cottage food disclosure language confirmed with each member**. The site-wide footer disclosure covers members in aggregate; each member should sign off on whether the shared wording works for their specific product category, or whether they need an additional per-panel note.
- [ ] Custom domain `chattcollective.com` wired (Settings → Pages → Custom domain), `baseurl: /chattcollective` removed from `_config.yml`
- [ ] Favicon set generated from the final wordmark

Quality bars before launch:
- [ ] Lighthouse a11y ≥ 95 on the homepage and 404
- [ ] Color contrasts verified against design system table
- [ ] All images have meaningful `alt` text (member + subject), or are explicitly decorative
- [ ] Tested on a real phone in real daylight (it's a food site; that's where it'll be read)
- [ ] No third-party tracking, no analytics — defer that decision

Explicitly out of scope for Phase 1: blog, online ordering, newsletter, multi-page architecture.

## Phase 2 — Content depth & visual polish

**Goal:** the site stops feeling like a stub.

**Done when:** every member panel has real photography, the Collective wordmark is integrated into the masthead, and the homepage has a tagline the members are happy with.

- [ ] Real photography sweep — daylight, hands-in-frame, anti-stock; populate the empty image slots in member panels (the design system reserves space for these)
- [ ] Wordmark / logo integrated into masthead and favicon
- [ ] Final tagline picked from brand guide candidates, wired into hero + meta description
- [ ] Per-member "what we make" detail — short bullet list within each panel, not a catalog (catalogs come later if at all)
- [ ] Member panels expanded — longer first-person copy from each member, multiple photos, links to their own social/site
- [ ] Image optimization: `.webp` with sensible widths, `loading="lazy"`, `<picture>` where appropriate
- [ ] Self-host fonts (Fraunces + Work Sans, subsetted) under `assets/fonts/`
- [ ] Performance budget set and verified (target: ≤ 75KB CSS, ≤ 200KB images on first viewport, no JS unless required)

## Phase 3 — Products surface (gated on demand)

**Goal:** surface specific things across members so a reader looking for "sourdough" or "hot honey" can find it without scanning every member panel.

**Gate:** don't start this until membership is large enough to make a products surface useful, OR readers/members specifically ask for it. While membership is small, member panels do this job better than a products index.

- [ ] Decide whether products lives as a separate Liquid collection or as inline sections per member (single-page architecture should be preserved unless there's a strong reason to break it)
- [ ] One product entry per *category a member offers* (not one per SKU — we're not a store)
- [ ] Bidirectional links: each member panel lists their product categories; each product category lists contributing members
- [ ] Decide whether prices appear here. Default: no, because they change and we're not selling.

## Phase 4 — Onboarding & growth

**Goal:** new cottage food makers in Chattanooga can find the Collective and apply to join without a pre-existing relationship.

**Done when:** at least one new member has come through the published onboarding path.

- [ ] `/#join` section (or its own page if it grows) — what the Collective is, what membership requires, what it doesn't (it's not a co-op, no shared kitchen, no fees if that stays true)
- [ ] Lightweight application — email-based, no form-builders
- [ ] Internal `docs/member-onboarding.md` — checklist for adding a new member: photos, blurb, contact, disclosure language confirmation, panel review
- [ ] Optional: a "member of Chattanooga Collective" badge / link snippet members can put on their own sites (open question in design system — resolve before building)

## Maybe-never (deliberately deferred)

These have been considered and intentionally aren't on the roadmap. They go here so we don't accidentally drift into them and so future contributors see the prior thinking.

- **E-commerce / online ordering** — TN cottage food law has narrow boundaries; the brand premise is buy direct from the maker. Re-open only if the legal landscape changes or a member explicitly wants it.
- **Out-of-state shipping** — same reason.
- **Blog / journal** — fine in principle, but only if a member or the Collective actually wants to write. Don't add the machinery speculatively.
- **Events calendar** — only if the Collective ever does pop-ups together beyond the recurring HiLo Market presence. One-off events can live in a member's section.
- **Newsletter** — minimal-tool only (e.g., Buttondown) and only if there's a clear reason someone would want one. No marketing automation.
- **JS framework / build pipeline** — the site shouldn't need it. If a feature seems to require one, that's a flag to question the feature.
- **Multi-page architecture** — the standalone About / Contact / Vendors pages were tried in an earlier draft and removed; folding everything into the homepage produced a clearer, shorter site. Don't reintroduce without a real reason.

## Cross-cutting concerns

These don't belong to a single phase; check them every phase.

- **Legal review checkpoint** — before any member panel goes live or changes, confirm cottage food disclosure language with the member (not boilerplate)
- **Voice review** — every new piece of Collective-authored copy gets read against the brand guide do/don't list before merge. Plainspoken-neighbor with Appalachian collectivity is the target; "front door" is permanently out; specific member counts are out (leave room for growth).
- **A11y audit** — before each phase ships, run an automated check + a manual keyboard pass
- **Performance budget** — set in Phase 2, enforced afterward; CI check is overkill for now, manual is fine
- **Member consent** — the site represents real people. Member-specific changes get their explicit OK before going live.
