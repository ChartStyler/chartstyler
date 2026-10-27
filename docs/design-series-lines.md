---
layout: default
title: Lines
parent: Series
grand_parent: Design
nav_order: 1
---

# Design → Series → Lines

Controls the line of each series. For Bar and Bar (Horizontal) charts this sub-tab is labelled **Fill** and sets the bar colour instead; see [Fill (bar charts)](#fill-bar-charts).

Select a series in the [Series selector](design-series.md#series-selector) first.

---

## Line Style

*(Visible for Line, Area, Scatter, Pie and Donut chart types.)*

- **Line Width (pt)**: stroke weight of the series line. Leave blank to use the value set on the `Chart Line N` object style in InDesign's Object Styles panel.
- **Connect Missing Values** *(Line, Area and Scatter)*: when checked, empty values are skipped and the line continues to the next valid point. When unchecked, the line breaks at gaps.
- **Sort largest to smallest** *(Pie and Donut, with All Values selected)*: orders the slices from the largest to the smallest value.

---

## Line Color

- **Color**: shows the effective colour for the selected series.
- **Override color**: lets you choose a different colour for the selected series. You can browse colours from another InDesign colour group without changing the chart's main [palette](design-palette.md).

---

## Fill (bar charts)

For Bar and Bar (Horizontal) charts, this sub-tab is labelled **Fill**. Bars have no separate stroke, so **Color** and **Override color** set the bar's fill.

### Data Point Group Overrides

Once a [data point group](data-series-groups.md) has a point in it, you can select it in the Series selector to give that group of bars, across any series, its own fill colour. Enable **Override color** and choose the colour.
