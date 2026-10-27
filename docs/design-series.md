---
layout: default
title: Series
parent: Design
nav_order: 3
has_children: true
---

# Design → Series

Controls the visual appearance of each data series. It has up to three sub-tabs, depending on the chart type:

- [Lines](design-series-lines.md): line width, gaps and line colour. For Bar charts this tab is called **Fill** and sets the bar colour.
- [Markers](design-series-markers.md): data point markers. Shown for Line, Area and Scatter charts.
- [Area](design-series-area.md): area fill style and opacity. Shown for Area charts.

---

## Series selector

The **Series** dropdown at the top applies to all three sub-tabs. Choose *All Series* to apply settings to every series at once, or choose one series to give it its own settings. Settings for a specific series override the defaults for that series only. For Pie and Donut charts, the dropdown lists the individual values (slices) instead.

When at least one [data point group](data-series-groups.md) has a point in it, the dropdown also lists one **"Data Point Group: <name>"** entry per group, below the series. These entries only appear on the one sub-tab that configures groups for the current chart type: **Markers** for Line, Area and Scatter, and **Fill** for Bar and Bar (Horizontal). Switching to another sub-tab removes the group from the dropdown, falling back to *All Series* if a group was selected.
