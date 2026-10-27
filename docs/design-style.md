---
layout: default
title: Style
parent: Design
nav_order: 5
---

# Design → Style

Controls which InDesign style groups are used to store and inherit chart styles. The settings are on the **General** sub-tab, currently the only sub-tab here.

---

## Style Group

The name of the InDesign paragraph and object style group where all chart styles are created. Defaults to the chart name.

Each chart gets its own style group, so multiple charts in the same document can have independent styling.

---

## Parent Style Group

An optional name of an existing style group. When set, all chart paragraph styles in the active Style Group become thin `basedOn` wrappers pointing to equivalently-named styles inside the parent group.

**How to use it:**

1. Enter a name in the Parent Style Group field and draw the chart once.
2. InDesign creates a style group at `chartStyler/<ParentStyleGroup>/` containing all the text styles (Basic, X-axis labels, Legend, Title, etc.).
3. Edit those parent styles in InDesign's paragraph styles panel — change the font, size, or color as needed.
4. Every chart whose Style Group points to this parent inherits the changes automatically.

This is useful when you have a design system and want charts to follow your existing typography without needing to edit each chart's styles individually.

See the [Object styles reference](object-styles.md) for every style ChartStyler creates.

---

## Colours and data point groups

- Series and slice colours come from the chart palette; see [Design → Palette](design-palette.md).
- Style overrides for data point groups are set on [Design → Series → Markers](design-series-markers.md#data-point-group-overrides), or on **Fill** for bar charts. See [Groups](data-series-groups.md) for details.
