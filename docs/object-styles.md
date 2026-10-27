---
layout: default
title: Object styles reference
nav_order: 5
---

# Object and paragraph styles reference

When ChartStyler draws a chart, it creates a hierarchy of named styles in InDesign. You can edit these styles to control the appearance of every chart element. Styles are created once and never overwritten on subsequent redraws — only the properties listed as *synced on every draw* are updated automatically. Properties not listed as synced are set once, at creation, and are yours to edit afterward.

Paragraph styles and object styles are separate InDesign panels — each gets its own group of the same name, so "Chart Line 1" (an object style, in the **Object Styles** panel) and "Basic" (a paragraph style, in the **Paragraph Styles** panel) don't sit in the same list even though both live under the same Style Group.

---

## Style group structure

All styles are placed inside a style group named after the chart (or the value of **Style Group** in the Style tab):

```
Object Styles panel — [Style Group Name]/
  Chart Background
  Axis Lines
  All Chart Lines
  All Chart Markers
  All Chart Bars
  All Chart Areas
  Chart Line 1
  Chart Line 1 Legend
  Chart Line 2
  ...
  Chart Marker 1
  Chart Marker 1 (Key)       ← per cell-style override
  Chart Marker 2
  ...
  Chart Bar 1
  Chart Bar 1 (Key)          ← per cell-style override
  Chart Bar 2
  ...
  Chart Area 1
  Chart Area 2
  ...
  X-axis labels
  Y-axis labels
  Axis title                 ← shared by both the X and Y axis title text frames
  Legend [position] -Col / -Row

Paragraph Styles panel — [Style Group Name]/
  Basic
  X-axis labels
  Y-axis labels
  Legend left / center / right / justified
  Legend Title
```

---

## Object styles

### Chart Background
The full-bleed background rectangle behind the chart. Fill color is deliberately **not** stored on this style (it's applied straight to the rectangle instead, from the *Background Color* setting) — nothing here is synced on every draw, so anything else you set (stroke, effects) is preserved.

### Axis Lines
The X and Y axis border lines.
- *Synced on every draw:* `strokeColor`, `strokeWeight` (only when a weight is actually specified; *auto* mode leaves your edited weight alone)

### All Chart Lines
Base style for all series lines. Change stroke properties here to affect every line in the chart.

### All Chart Markers
Base style for all series markers. Change fill or size here to affect all markers.
- *Synced on every draw:* `strokeColor` (forced to None), `strokeWeight` (forced to 0)

### All Chart Bars
Base style for all bar chart bars.
- *Synced on every draw:* `strokeColor` (forced to None), `strokeWeight` (forced to 0)

### All Chart Areas
Base style for all area chart fills.
- *Synced on every draw:* `strokeColor` (forced to None), `strokeWeight` (forced to 0), `opacity`, `blendMode` (from the *Area Opacity %* setting) — editing these here has no persistent effect.

### Chart Line N
Per-series line style, based on **All Chart Lines**.
- *Synced on every draw:* `strokeColor`, `strokeWeight` (when Line Width is set; *auto* mode preserves your edits)

### Chart Line N Legend
Per-series legend swatch line, based on **Chart Line N**. Kept separate so you can remove arrowheads or change weight for the legend independently of the chart line.
- *Synced on every draw:* `strokeColor`, `strokeWeight` (same *auto*-mode caveat as Chart Line N)

### Chart Marker N
Per-series marker style, based on **All Chart Markers**.
- *Synced on every draw:* `fillColor`, `strokeColor` (forced to None), `strokeWeight` (forced to 0)

### Chart Marker N (Key)
Per-point marker override, based on **Chart Marker N**. Created when a data point is tagged with the `ChartStyler_Key` cell style.
- *Synced on every draw:* `fillColor`, `strokeColor` (forced to None), `strokeWeight` (forced to 0)
- Everything else (effects, etc.) is yours to edit.

### Chart Bar N
Per-series bar style, based on **All Chart Bars**.
- *Synced on every draw:* `fillColor`
- Stroke cleared at creation only — you can add a stroke in InDesign and it will be preserved.

### Chart Bar N (Key)
Per-point bar override, based on **Chart Bar N**. Created when a data point is tagged with the `ChartStyler_Key` cell style.
- *Synced on every draw:* `fillColor`
- Stroke cleared at creation only, same as Chart Bar N.

### Chart Area N
Per-series area fill style, based on **All Chart Areas**.
- *Synced on every draw:* `fillColor`, `opacity`, `blendMode`
- Stroke cleared at creation only.

### X-axis labels / Y-axis labels / Axis title
Frame-level styles for the tick labels and axis titles (fill/stroke set to None, auto-sizing behavior). Nothing on these is synced after creation.

### Legend [position] -Col / -Row
Legend text frame, one per legend position and orientation actually in use (`-Col` for a vertical stack, `-Row` for a horizontal run). Nothing on these is synced after creation.

---

## Paragraph styles

All paragraph styles are placed in the same style group as the object styles, in the separate **Paragraph Styles** panel.

| Style | Used for |
|---|---|
| `Basic` | Root style; all other text styles inherit from it via `basedOn`. Change the font here to update all chart text — **except** axis titles, see note below. |
| `X-axis labels` | Tick labels along the X axis |
| `Y-axis labels` | Tick labels along the Y axis |
| `Legend left` / `center` / `right` / `justified` | Legend item text — whichever alignment the legend actually uses |
| `Legend Title` | Legend title text |

> **Tip:** Edit `Basic` to change the typeface for most chart text in one step. Individual styles inherit from Basic via InDesign's `basedOn` chain.

> **Note — Axis titles have no paragraph style.** Unlike the other text elements, the X-axis and Y-axis title text frames are not assigned any paragraph style — only the **Axis title** *object* style above applies to them. Their font comes from InDesign's own default text formatting, not from `Basic`. If you need to change their typeface, select the text and apply a font directly, or apply `Basic` to it by hand.

> **Note — the live preview reads these back.** `Basic`, `X-axis labels`, and `Y-axis labels` are the only styles ChartStyler ever reads properties from (font and size) rather than just writes to — it uses them to keep the chart preview panel's fonts matching what you've set in InDesign. Every other style is write-only from the plugin's side.

---

## Using a Parent Style Group

See [Design — Style](design-style.md#parent-style-group) for how to route all paragraph style inheritance through a shared parent group, making it easy to apply a single typography system across multiple charts.
