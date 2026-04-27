# Chattanooga Collective

The website for a devoted group of artisan cottage food makers in Chattanooga, TN. Built with Jekyll, hosted on GitHub Pages, deployed at [chattcollective.com](https://chattcollective.com) (preview at [seguri-io.github.io/chattcollective](https://seguri-io.github.io/chattcollective/) until the custom domain is wired).

This site is a shared directory — not a storefront. Each member runs their own kitchen, sets their own prices, and handles their own orders. The Collective is the modern shape of an old mountain habit: neighbors helping neighbors.

## Current members

- **[Starving Dragon](https://starvingdragon.com)** — Sichuan chili crisp oil, craft-batch, made in Chattanooga.
- **Ridge &amp; Valley** — functional allergen-free foods (sea vegetables, adaptogenic mushrooms, ayurvedic spices), Appalachian-rooted. Site forthcoming.

## Status

Live preview shipping. The brand and design system are settled (see `docs/`); the site is a single-page Jekyll build with all members rendered inline. See [`ROADMAP.md`](./ROADMAP.md) for what's done, what's next, and what's deliberately not on the list.

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
| [`docs/brand-guidelines.md`](./docs/brand-guidelines.md) | Mission, three-brand structure, voice rules per brand, photography direction |
| [`docs/design-system.md`](./docs/design-system.md) | Palette tokens (three brands), typography, spacing, component patterns |
| [`docs/handoff/`](./docs/handoff/) | Original Claude Design bundle preserved as reference (the docs above are authoritative) |

If you're picking this up for the first time, read in this order: `README.md` → `docs/brand-guidelines.md` → `docs/design-system.md` → `ROADMAP.md` → `CLAUDE.md`.

## Repo layout

```
.
├── CLAUDE.md / ROADMAP.md / README.md   project meta
├── Gemfile                              Jekyll + GitHub Pages dependencies
├── _config.yml                          Jekyll config
├── _data/navigation.yml                 anchor-based main nav
├── _layouts/                            default · home (passthrough)
├── _includes/                           head · nav · footer · section_header · member · disclosure
├── _members/                            one Markdown file per member (collection, output: false)
├── assets/
│   ├── css/main.scss                    full design system (3 palettes, components, type)
│   └── images/vendors/<slug>/           per-member photography and logos
├── docs/
│   ├── brand-guidelines.md
│   ├── design-system.md
│   └── handoff/                         original design handoff bundle
├── index.html                           the entire public site
└── 404.html
```

The site is **single-page**: every section lives on `index.html`; nav links are anchor jumps. The `_members/` collection has `output: false` — the homepage Liquid loop renders each member as a full-width inline panel.

## A note on Tennessee cottage food law

Members operate under [Tennessee's Domestic Kitchen / Tennessee Food Freedom Act](https://www.tn.gov/agriculture/businesses/food-safety/domestic-kitchens.html) rules. This shapes what the site can do:

- No payments, no shipping, no marketplace functionality
- Each member panel carries the required home-kitchen disclosure
- Sales are direct between maker and customer, generally in-person and in-state

If you're a Chattanooga cottage food maker thinking about joining, see [`ROADMAP.md`](./ROADMAP.md) — the join flow is on the path but isn&rsquo;t built yet. In the meantime, reach out at <a href="mailto:hello@chattcollective.com">hello@chattcollective.com</a>.

## Contributing

This is a small project for a small collective. If you're a member, edits to your own panel and copy are welcome — open a PR or message the maintainer. If you're not a member, the easiest way to support the Collective is to buy from one of the members above.

## License

The site code (Jekyll templates, SCSS, Liquid includes) is MIT — feel free to borrow patterns. Member logos, photography, and copy belong to the respective members and are not covered by that license.
