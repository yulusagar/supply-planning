# Supply Planning — Ops console

Interactive prototype for Yulu supply planning. Single self-contained HTML file;
no build step and no dependencies.

**Live:** https://yulusagar.github.io/supply-planning/

## Sections

- **Slot creation** — define slots inside a centre's operating hours. View-only by
  default; *Create slots* enables slicing, resizing and merging (tick rows to apply
  one cut across several days). *Define slot type* marks slots Planned or Blocked.
- **Planning templates** — day-of-week presets.
- **Day-to-day planning** — enter planned numbers per slot and bike model.
  Save commits them; Publish makes them live. The dot in each field shows which:
  grey = not published, orange = saved, green = published.

Blocked slots carry no planning table in either planning section.

State is kept in the browser's localStorage — "Reset saved data" clears it.

## Running locally

Open `index.html` directly, or serve it (localStorage is more reliable over http):

    python3 -m http.server 8080
