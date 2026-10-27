---
layout: default
title: Markers
parent: Series
grand_parent: Design
nav_order: 2
---

# Design → Series → Markers

*(Shown for Line, Area and Scatter chart types.)*

Controls the markers drawn at each data point. Select a series in the [Series selector](design-series.md#series-selector) first.

---

## Marker Style

- **Show Data Points**: draws a marker at each data point.
- **Shape**: *Circle*, *Square*, *Diamond*, *Triangle Up*, *Triangle Down*, *Triangle NE/SE/SW/NW*, *Pentagon*, *Hexagon*, *Hexagon 2*, *Octagon*, *Cross*, *X*, or *None* (hides markers).
- **Size (pt)**: marker diameter in points. Disabled when Shape is *None*.

---

## Marker Color

Marker colour is independent of line colour. Without an override, markers use the series colour.

- **Color**: shows the effective marker colour for the selected series.
- **Override color**: lets you choose a different marker colour for the selected series.

---

## Data Point Group Overrides

Selecting a **"Data Point Group: <name>"** entry in the Series selector switches the Shape and Size fields to configure that group instead of a series. The settings apply only to data points assigned to the group, regardless of which series they belong to. A "Data Point Group Overrides" heading appears to make the switch obvious.

Enable **Override color** to also give the group its own colour, from the chart palette or another InDesign colour group. Unlike a series, a group has no colour to fall back on until you set one.

See [Groups](data-series-groups.md) for how to assign points to a group.
