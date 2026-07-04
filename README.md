# BLOOM

A small gallery of beautiful, single-file HTML/CSS dashboard aesthetics — no build step, no frameworks, no dependencies. Pick a style, open the file, and it works fully offline — Inter is self-hosted (see `fonts/`), with a system-font fallback stack if it's ever unavailable.

Open `index.html` to browse available dashboards.

## Dashboards

- **[3D Dashboard](dashboards/3d-dashboard.html)** — soft neumorphic "life OS" with a warm gradient background, pillowy raised cards, circular orbs, and inset progress bars. Sections: daily greeting, mood check-in, habit tracker, goal progress, weekly focus, and a motivational quote.

More styles coming soon.

## Adding a new dashboard style

The gallery in `index.html` is rendered from a small JS array (`DASHBOARDS`) rather than hand-coded tiles, so adding a style doesn't require touching any HTML markup.

1. Create a new file under `dashboards/` (e.g. `dashboards/my-style.html`). Follow the existing conventions: single self-contained file, no external dependencies, no network requests — it should work fully offline (see `dashboards/3d-dashboard.html` for reference, including how it self-hosts Inter via `fonts/`).
2. Optionally generate a preview screenshot and save it under `previews/` (e.g. `previews/my-style.png`). A reasonable thumbnail size (around 900px wide) keeps the repo light.
3. Register the style by adding an entry to the `DASHBOARDS` array in `index.html`. Each entry has the shape:
   - `title` — the display name shown in the tile (e.g. `"My Style"`)
   - `tag` — a short label above the title (e.g. `"Glassmorphic"`, or `"Coming soon"` for a placeholder)
   - `desc` — a one-sentence description of the aesthetic
   - `href` — path to the dashboard file (e.g. `"dashboards/my-style.html"`), or `null` for a placeholder
   - `status` — `"live"` for a real, linkable tile, or `"soon"` for a non-interactive placeholder
   - `preview` — path to a preview image (e.g. `"previews/my-style.png"`), or `null` to fall back to the default gradient+orb placeholder

That's it — the gallery script renders the tile markup for you.
