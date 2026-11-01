# Supply Planning — Ops console

Interactive prototype for Yulu supply planning. Single self-contained HTML file;
no build step and no dependencies.

**Live:** https://yulusagar.github.io/supply-planning/

## Sections

There is no side navigation. The app opens on Day-to-day planning; its ⋮ menu has a
**Manage slots & template** row, and Template planning has a back arrow at the top left.

- **Template planning** — day-of-week presets for one centre, and where slots are
  defined. *Edit slots* turns the weekday rows into an editable canvas: click a slot
  to slice it, drag dividers to resize, tick rows to cut several days at once. Each
  slot's type pill switches it between Planned and Blocked. Template inputs are
  disabled while editing.
- **Day-to-day planning** — enter planned numbers per slot and bike model. A filter
  strip under the header is always visible and takes effect as you pick; it includes
  **Planning for** (Corporate / Business). The ⋮ menu sets how the rows are grouped. The
  template number shows as helper text in an empty field (→ accepts it). There is no
  save step: type the numbers and **Publish**, now or on a schedule. Total capacity
  counts published numbers only.

Blocked slots carry no planning table in either section.

State is kept in the browser's localStorage. There is no reset button; clear the
site's data in your browser to start fresh.

## Running locally

Open `index.html` directly, or serve it (localStorage is more reliable over http):

    python3 -m http.server 8080

## Planning rules (Day-to-day)

- **Business** is planned per company: pick the company after City, and every YC shows as an accordion with that company's numbers. There is no YC picker in the header.
- The slot the clock is in is editable; only slots already over are read-only.
- Lowering a number below what it was asks for a reason (Excessive swap orders / Spare part storage / Other), saves it and lets you keep editing.
- A number can't go below what is already booked. The field turns red when you leave it, and Update stays off until it's fixed.
- Edited cells keep a light blue tint until published or cancelled. **Cancel** (left of **Update N slot values**) discards every unpublished change.
- Rollovers (ⓘ) now open as extra columns in the left rail.

## Mobile (up to 720px wide)

A separate layout, not the desktop squeezed down: day strip, filter chips that open a bottom sheet, centres as stacked cards with capacity and slot blocks (Live / Done / Upcoming), dialogs as bottom sheets, and a pinned Cancel / Update bar. Editing slot times (slice, merge, resize) stays desktop-only.
