# Design — Sofia Perez-Vigo Meteorological Station

Single self-contained `index.html`. The visual world is pinned by the brief: a Victorian-scientific mahogany instrument board of brass-and-enamel analogue dials. Every reading is a needle; there are no rectangles of numbers.

## Palette

| Token | Value | Use |
|---|---|---|
| `--cream` | `#EDE4CF` | Enamel dial faces |
| `--cream-hi / --cream-lo` | `#F6EED9 / #D8CBAC` | Enamel shading |
| `--brass` | `#B08D3C` | Bezels, plates, fittings |
| `--brass-hi / --brass-sh` | `#D9BC6A / #6E5620` | Brass highlight / shadow |
| `--ink` | `#23312F` | Engraved lettering, case lining, baize |
| `--red` | `#A33B2B` | Warning sectors, storm cone, vane, gale ink |
| `--sea` | `#6F8F8C` | Secondary marks, rain, mercury |
| `--wood` | `#3B2A20` | Board base, with procedural grain |
| `--violet` | `#5b3a72` | Barograph and history ink |

Dark wood carries light enamel dials; the page reads warm because the dials dominate.

## Typography

Georgia / "Times New Roman" serif throughout. Engraved-style capitals with wide tracking for dial lettering, name plates and the brass title plaque; italic serif for the observer's log (slight per-entry rotation for a handwritten feel); numerals rotated around each dial. Functional text is kept at ≥11px; micro engraving on dials is decorative.

## Components

- **Instrument** — inline SVG: brass bezel with highlight/shadow, cream enamel face, engraved scale with rotated numerals, maker's name "TARRANT & LYLE, LEITH", four screws, a window-pane glass reflection, and rain-streak lines revealed only in a storm.
- **Needles** — damped-spring physics with per-instrument character: barometer heavy and sticky, vane nervous, anemometer surging, thermometers and tide slow and steady. Tiny tremble scales with wind.
- **Name plate** — brass engraved strip, also the click target for enlargement (the barometer's plate only; its glass is for tapping).
- **Time lever** — brass handle on a rail at the board's foot, with a red slot marking the gale period, keyboard-operable, plus an AUTO/HOLD switch.
- **Tooltip** — small engraved brass plate following the pointer over a dial.
- **Detail overlay** — enlarged dial beside a record card with exact reading, note and a 24-hour inked history chart; the barograph unrolls all seven days.
- **Plaque, station clock, signal mast** — header; the mast's red cone hoists in a baize-lined porthole during the storm.

## Motion

One authored moment: the storm. Below 980 hPa the cone hoists (point down for a southerly gale, point up once the wind veers NW), lighting dims, glass highlights shift, rain streaks appear, and the log writes gale entries in red. Needle inertia, cup-anemometer spin, drum rotation and the barograph pen trace all belong to the same system. Reduced motion: needles snap to target, drum stops (the week's chart lies still and the pen travels), tremble and optional spin are disabled.

## Layout

Board grid with named areas: barometer large in the centre, anemometer/wind vane flanking, thermometers/rain gauge beneath, wide barograph, sunshine recorder and a compact trio (tide, sea, visibility). The brass time rail is sticky **within the board only**, with weekday segments and the red gale band drawn into the track.

The register is an open book on a baize-green desk: a ruled log page (handwriting face, marginal red rule) and a typeset synopsis page with a drop cap, forecast table and fine print. **Neither page has an internal scroll container** — the whole document scrolls naturally, so the wheel never gets trapped in the log.

Responsive: 4-column board → 2 columns (<1040px) → single column (<640px) with the barometer first; the book stacks to one column and the detail view becomes vertical.

## Content

All weather is fictional, generated in-page from a smooth periodic simulation of a passing depression over a seven-day loop at ~1.8 s per simulated hour. Log entries and the twelve-hour synopsis are generated from the same state and labelled simulated.
