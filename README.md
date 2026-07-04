# BLOOM

A small gallery of beautiful, single-file HTML/CSS dashboard aesthetics — no build step, no frameworks, no dependencies. Pick a style, open the file, and it works fully offline — Inter is self-hosted (see `fonts/`), with a system-font fallback stack if it's ever unavailable.

Open `index.html` to browse available dashboards.

## Dashboards

Every category is the same underlying personal "life OS" dashboard — daily greeting, mood check-in, habit tracker, goal progress, weekly focus, and a motivational quote — reskinned 5 different ways. Pick a category, then pick a design within it.

- **[3D Dashboard](dashboards/3d-dashboard/index.html)** — soft, pillowy, dimensional materials. 5 designs: Warm Neumorphic, Deep Space Console, Holographic Iridescent, Brushed Metal Console, Gummy Toy.
- **[Glassmorphic](dashboards/glassmorphic/index.html)** — frosted, translucent layers over gradient backdrops. 5 designs: Daylight Glass, Obsidian Glass, Aurora Glass, Amber Glass, Frost Glass.
- **[Editorial Minimal](dashboards/editorial-minimal/index.html)** — typographic, high-contrast, print-inspired layouts. 5 designs: Swiss Grid, Broadsheet, Brutalist Type, Runway, Ledger.

## Adding a new design to a category

Each category (`dashboards/3d-dashboard/`, `dashboards/glassmorphic/`, `dashboards/editorial-minimal/`) has its own sub-gallery `index.html`, built the same way as the root gallery — a small JS array of tiles rendered into the page.

1. Create a new file under the category folder (e.g. `dashboards/glassmorphic/my-design.html`). Follow the existing conventions: single self-contained file, self-hosted Inter only (`../../fonts/`), no other external dependencies or network requests — it should work fully offline. Reuse the same content/data as the other designs in that category (same habits, goals, quotes, etc.) and reskin the visual language.
2. Generate a preview screenshot and save it under that category's `previews/` folder (e.g. `dashboards/glassmorphic/previews/my-design.png`, ~900px wide).
3. Register it in the category's own `DASHBOARDS`-style array in that category's `index.html`.

## Adding a new category

1. Create a new folder under `dashboards/` with its own `index.html` sub-gallery (model it on an existing category's `index.html`) and a `previews/` folder.
2. Build out its designs following the convention above.
3. Register the category by adding an entry to the `DASHBOARDS` array in the root `index.html`. Each entry has the shape:
   - `title` — the display name shown in the tile (e.g. `"My Category"`)
   - `tag` — a short label above the title (e.g. `"5 designs"`, or `"Coming soon"` for a placeholder)
   - `desc` — a one-sentence description of the aesthetic, naming the designs inside it
   - `href` — path to the category's sub-gallery (e.g. `"dashboards/my-category/index.html"`), or `null` for a placeholder
   - `status` — `"live"` for a real, linkable tile, or `"soon"` for a non-interactive placeholder
   - `preview` — path to a representative preview image, or `null` to fall back to the default gradient+orb placeholder
