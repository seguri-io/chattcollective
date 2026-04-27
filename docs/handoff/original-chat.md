# Chattanooga Collective Brand

_Started 2026-04-27 17:59 UTC_

---

## User



## Assistant

_[tool: update_todos]_

_[tool: list_files]_

_[tool: web_fetch]_

_[tool: questions_v2]_

_[tool: web_search]_

_[tool: web_search]_

I hit two blockers I need to flag before diving in:

1. **starvingdragon.com is currently unreachable** — the site returned a network error, so I can't pull colors, type, copy, or any visual assets from it.
2. **No files were attached to the project** — there are no logos, screenshots, Figma links, or any other materials in the project directory.

Without source materials I'd essentially be inventing a design system from scratch, which would produce something generic and off-brand. Before I proceed, I need a bit more from you:

## User

Questions answered:
- starving_dragon_status: I have screenshots I can upload instead
- ridge_and_valley_materials: Nothing yet — it's still being built
- collective_brand: Not yet — help me create one
- starving_dragon_description: Sichuan products, primarily Chili oil
- scope: A shared Chattanooga Collective website
- ridge_valley_description: All sorts of things, but the focus is functional (ie, enriched with functional superfoods like sea vegetables, functional mushrooms, ayurvedic spices, etc) foods that are allrergen free and taste just as good or better than the alternatives.
- aesthetic: Earthy & rustic (natural textures, warm tones, handwritten type)
- figma: https://www.instagram.com/starvingdragonoil/

https://starvingdragon.com/
https://github.com/tritzriley/starvingdragon/blob/main/index.html

## Assistant

_[tool: set_project_title]_

_[tool: update_todos]_

Great info! Let me dig into the Starving Dragon GitHub source and try the website again — both at the same time.

_[tool: web_fetch]_

_[tool: web_fetch]_

_[tool: web_fetch]_

_[tool: web_fetch]_

I got the full Starving Dragon source code. Now I have everything I need to build the design system. Let me work through this systematically.

_[tool: run_script]_

Let me extract the logo and build everything in parallel.

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

Now let me build all the preview cards and UI kit in parallel batches.

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

Now the big one — the Starving Dragon UI kit, faithfully recreating the site from source code:

_[tool: write_file]_

Now the Collective website UI kit and SKILL.md, then register everything:

_[tool: write_file]_

_[tool: write_file]_

_[tool: write_file]_

Now register everything in the Design System tab:

_[tool: register_assets]_

_[tool: update_todos]_

_[tool: done]_

_[tool: fork_verifier_agent]_

The design system is built! Here's what's in it:

**15 registered cards** across Colors, Type, Components, and Brand — visible in the Design System tab.

**Key caveats & asks:**

1. **🔴 Real logo needed** — The Starving Dragon logo is embedded as base64 in the site HTML and couldn't be extracted. Please provide the original PNG/SVG file and I'll slot it in everywhere.

2. **🟡 Collective brand is proposed** — The leaf mark, parchment palette (Lora + DM Sans), and green/ochre color scheme are a starting point for the umbrella brand. Want to **iterate on the direction**, try alternate palettes, or explore a different logo mark?

3. **🟡 Ridge and Valley is a placeholder** — No visual materials exist yet. Once the vendor has product ideas, logo thinking, or even a mood board, I can build out their brand section fully.

4. **⚪ Font substitutions flagged** — Playfair Display and Inter are used exactly as in the Starving Dragon source. For the Collective, Lora + DM Sans are Google Fonts substitutes — if the brand acquires licensed typefaces later, swap them in `colors_and_type.css`.

5. **⚪ starvingdragon.com was down** — Everything was built from the GitHub source. If the live site has updated content or product photos, let me know and I'll update the kit.

**What would you like to refine first?** The Collective brand identity is the most open question — happy to explore alternate color directions, logo concepts, or a different overall aesthetic.

## User



## Assistant

_[tool: copy_files]_

What a logo! Illustrated badge style, vintage food label, cartoon dragon — much more playful than the dark website aesthetic alone suggests. Let me get this into the design system properly.

_[tool: str_replace_edit]_

Now update the UI kit with the real logo, create a proper brand card, and update the README:Now create a proper logo brand card and update the README:

_[tool: write_file]_

_[tool: register_assets]_

_[tool: unregister_assets]_

_[tool: str_replace_edit]_

Now update the README and unregister the placeholder:

_[tool: str_replace_edit]_

_[tool: str_replace_edit]_

Also update the VISUAL FOUNDATIONS section of README to capture the logo's illustrated style insight, and fix the UI kit README caveat:

_[tool: done]_

The real logo is now in! A few observations it reveals about the brand:

**The logo tells a richer story than the website alone:**
- The badge style is warm, illustrated, and genuinely funny ("OM NOM / NOM") — the dark moody website is the *premium shelf* face, but the logo is the *soul* of the brand
- Parchment/kraft paper texture in the logo background suggests that aesthetic could extend into the Collective brand (which I've already picked up on with the `#f5f0e8` parchment palette)
- The color palette in the logo — deep reds, burnt orange, gold/ochre, warm cream — maps almost perfectly to the CSS tokens already defined

**Remaining asks:**

1. **🟡 Collective logo direction** — Should the Collective's visual identity borrow more from this illustrated style (vintage badge, warm earthy tones)? Or keep it cleaner/more minimal as a neutral umbrella? I can explore both.

2. **🟡 Ridge and Valley** — Any logo, mood board, or product ideas yet? Even a rough description of what their packaging might look like would let me build out their section properly.

3. **⚪ Product photography** — Once you have jar photos, I can add them to the hero and origin sections of the Starving Dragon kit for full fidelity.

