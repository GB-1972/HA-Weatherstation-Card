# Changelog

## [v1.2.0] - 2026-05-19

### Added

- **Independent wind-direction invert** — the compass arrow and the direction text/degrees can now be inverted separately via two new options `wind_arrow_invert` and `wind_text_invert` (two toggles in the editor). This allows e.g. the arrow to show where the wind blows *to* while the text shows where it comes *from*.

### Changed

- The single `wind_direction_invert` option was replaced by `wind_arrow_invert` + `wind_text_invert`.

### Migration

- Backward compatible: an existing `wind_direction_invert: true/false` is automatically applied to **both** new options, so existing dashboards keep their current behavior with no action required.

## [v1.1.0] - 2026-05-18

### Added

- **Wind-direction invert** — new `wind_direction_invert` option (toggle in the editor). When enabled, 180° is added to the wind direction so the arrow and caption show the direction the wind blows *to* instead of where it comes *from*.
- **UV index chip** — new `uv_index` entity option.
- **Per-metric color thresholds** — the chip icon color can now react to the value. Each metric gets a list of `{ value, color }` thresholds; the color applies from that value upward. Configured in a new **"Farben"** (Colors) tab in the visual editor, with add/remove buttons and a native color picker per row. Without thresholds the previous static colors are used (fully backward compatible).

### Changed

- Editor is now **tabbed**: "Entitäten" (entities) and "Farben" (colors).

## [v1.0.0] - 2026-05-13

Initial public release.

### Features

- 16-point compass rose drawn as inline SVG with a rotating red wind-direction arrow
- Seven configurable sensor chips in Mushroom style: temperature, humidity, pressure, wind speed, wind gusts, current rain, rain last 24 h
- Visual editor (`ha-form` based) with `entity` selectors for every sensor — no YAML required
- Wind direction accepts either degree values (0–360) or text labels (`N`, `NO`/`NE`, `O`/`E`, … in German or English)
- Units auto-detected from each entity's `unit_of_measurement` attribute, with sensible fallbacks (°C / % / hPa / km/h / mm)
- Click on the compass or any chip opens the entity's more-info dialog
- Empty entity fields are hidden automatically
- Responsive layout — switches from 2-column chip grid to single column on narrow screens
