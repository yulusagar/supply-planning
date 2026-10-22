# Supply Planning — Ops console

Interactive prototype for Yulu supply planning. Single self-contained HTML file;
no build step and no dependencies.

**Live:** https://yulusagar.github.io/supply-planning/

## Sections

- **Template planning** — day-of-week presets for one centre, and where slots are
  defined. *Edit slots* turns the weekday rows into an editable canvas: click a slot
  to slice it, drag dividers to resize, tick rows to cut several days at once. Each
  slot's type pill switches it between Planned and Blocked. Template inputs are
  disabled while editing.
- **Day-to-day planning** — enter planned numbers per slot and bike model. The
  template number shows as helper text in an empty field (→ accepts it). There is no
  save step: type the numbers and **Publish**, now or on a schedule. Total capacity
  counts published numbers only.

Blocked slots carry no planning table in either section.

State is kept in the browser's localStorage — "Reset saved data" clears it.

## Running locally

Open `index.html` directly, or serve it (localStorage is more reliable over http):

    python3 -m http.server 8080
