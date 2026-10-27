---
layout: default
title: Groups
parent: Series
grand_parent: Data
nav_order: 4
---

# Data → Series → Groups

ChartStyler lets you group individual data points and override their appearance — a "data point group" is a named set of points you build by clicking them directly in the panel, not by editing anything in the InDesign document. This works for line, area, and scatter charts (full shape/size/color configuration) and for bar and bar-horizontal charts (a fill-color-only override, since bars have no marker to configure).

---

## Setup

### 1. Open Data → Series → Groups

This sub-tab is shown for Line, Area, Scatter, Bar and Bar (Horizontal) charts. It shows a table of your chart's resolved series and data points — the same values you'd see in the Processing tab's preview.

### 2. Create a group

Type a name and click **+ New**. The new group becomes "active."

### 3. Click points to add them

Click any point in the table to add it to the active group (click again to remove it). A point can only belong to one group at a time — clicking a point that's already in a different group moves it to the active one. Colors in the table show which group each point currently belongs to.

Membership is keyed by series name + point label, so it survives the source table being reordered or refreshed — unlike the old cell-style-based mechanism, nothing needs to be re-applied if you add or remove rows.

---

## Configuring the override appearance

Once at least one group has a point in it, it appears as a **"Data Point Group: <name>"** entry at the bottom of the **Series** dropdown, right alongside "All Series" and your individual series. Which sub-tab you need to be on for it to show up depends on chart type — a group only ever appears while the ONE sub-tab relevant to it is active:

| Chart type | Sub-tab | What you can override |
|---|---|---|
| Line, Area, Scatter | [Design → Series → **Markers**](design-series-markers.md#data-point-group-overrides) | Shape, Size, and Color |
| Bar, Bar-Horizontal | [Design → Series → **Fill**](design-series-lines.md#data-point-group-overrides) | Color only |

- Select the group from the **Series** dropdown.
- *(Line/Area/Scatter)* Set its **Shape** and **Size (pt)** in the same fields used for a series — applied only to data points assigned to that group, regardless of which series they belong to. Setting Shape to *None* hides markers for that group entirely.
- Enable **Override color** to also give the group its own color, from the chart palette or another InDesign color group.

Switching to a sub-tab that doesn't configure groups (e.g. Lines/Area for a Line chart, or Markers for a Bar chart — which is hidden entirely, since bars have no marker) drops the group from the dropdown, falling back to "All Series" if it was selected.

---

## How it works in InDesign

When a chart is inserted, ChartStyler creates additional object styles for each group that has at least one point, named after the group itself:

| Chart type | Style created | Based on |
|---|---|---|
| Line / Area / Scatter | `Chart Marker N (<group name>)` | `Chart Marker N` |
| Bar / Bar-Horizontal | `Chart Bar N (<group name>)` | `Chart Bar N` |

These styles are created the first time a matching data point is drawn. You can then edit them in InDesign's **Object Styles** panel to control fill color, stroke, transparency, or any other property — independently of the base series style. The fill color is synced from the group's configured override color on every redraw, but all other properties you set on the override style are preserved.

> **Tip:** To suppress a bar entirely, you cannot set opacity to 0 via the object style — instead set the fill to `[None]` or use a spot color at 0% tint in the override style.
