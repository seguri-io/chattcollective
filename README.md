# Chattanooga Collective

The website for a small group of independent cottage food makers in Chattanooga, TN. Built with Jekyll, hosted on GitHub Pages, deployed at [chattcollective.com](https://chattcollective.com).

This site is a directory and a front door — not a storefront. Each vendor runs their own kitchen, sets their own prices, and handles their own orders. The Collective's job is to make it easier for neighbors to find them.

## Current vendors

- **[Starving Dragon](https://starvingdragon.com)** — Sichuan chili crisp oil, craft-batch, made in Chattanooga.
- **Ridge & Valley** — functional allergen-free foods (sea vegetables, adaptogenic mushrooms, ayurvedic spices), Appalachian-rooted. Site forthcoming.

## Status

Early. The brand and design system are settled (see `docs/`); the Jekyll site itself isn't bootstrapped yet. See [`ROADMAP.md`](./ROADMAP.md) for what's done, what's next, and what's deliberately not on the list.

## Local development

Standard Jekyll + Bundler. From the repo root:

```bash
bundle install                            # first time, or after Gemfile changes
bundle exec jekyll serve --livereload     # http://127.0.0.1:4000
bundle exec jekyll build                  # one-shot build to _site/
```

Requires Ruby 3.x and Bundler. On Windows, the bundled `wdm` and `tzinfo-data` gems handle file watching and timezones automatically.

GitHub Pages builds on every push to `main` — no separate deploy step.

## Documentation

| File | What's in it |
| --- | --- |
| [`CLAUDE.md`](./CLAUDE.md) | Guidance for AI coding assistants working in this repo |
| [`ROADMAP.md`](./ROADMAP.md) | Phased plan from MVP through growth, plus a "deliberately deferred" list |
| [`docs/brand-guidelines.md`](./docs/brand-guidelines.md) | Mission, voice rules per brand, name treatment, photography direction |
| [`docs/design-system.md`](./docs/design-system.md) | Palette tokens, typography, spacing, component patterns |
| [`docs/handoff/`](./docs/handoff/) | Original Claude Design bundle preserved as reference (the docs above are authoritative) |

If you're picking this up for the first time, read in this order: `README.md` → `docs/brand-guidelines.md` → `docs/design-system.md` → `ROADMAP.md` → `CLAUDE.md`.

## Repo layout

```
.
├── CLAUDE.md / ROADMAP.md / README.md   project meta
├── Gemfile                              Jekyll + GitHub Pages dependencies
├── _config.yml                          Jekyll config (added at bootstrap)
├── _vendors/                            one Markdown file per vendor (collection)
├── _pages/                              top-level pages (about, contact, etc.)
├── _data/                               site data (navigation, etc.)
├── assets/
│   ├── css/                             SCSS that imports design system tokens
│   └── images/vendors/<slug>/           per-vendor photography and logos
├── docs/
│   ├── brand-guidelines.md
│   ├── design-system.md
│   └── handoff/                         original design handoff bundle
└── index.md                             homepage
```

Items marked "added at bootstrap" don't exist yet — they show up when Phase 1 starts.

## A note on Tennessee cottage food law

Members operate under [Tennessee's Domestic Kitchen / Tennessee Food Freedom Act](https://www.tn.gov/agriculture/businesses/food-safety/domestic-kitchens.html) rules. This shapes what the site can do:

- No payments, no shipping, no marketplace functionality
- Vendor pages carry the required home-kitchen disclosure
- Sales are direct between maker and customer, generally in-person and in-state

If you're a Chattanooga cottage food maker thinking about joining the Collective, see [`ROADMAP.md`](./ROADMAP.md) — the join flow is on the path but isn't built yet. In the meantime, reach out via the contact details on the live site (when it's live).

## Contributing

This is a small project for a small collective. If you're a member vendor, edits to your own profile and copy are welcome — open a PR or message the maintainer. If you're not a member, the easiest way to support the Collective is to buy from one of the vendors above.

## License

The site code (Jekyll templates, SCSS, Liquid includes) is MIT — feel free to borrow patterns. Vendor logos, photography, and copy belong to the respective vendors and are not covered by that license.
