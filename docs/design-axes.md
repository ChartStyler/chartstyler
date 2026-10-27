---
layout: default
title: Axes
parent: Design
nav_order: 2
has_children: true
---

# Design → Axes

*(Not shown for Pie and Donut charts, which have no axes.)*

Controls axis titles, grid lines, the axis range, and tick labels. It has three sub-tabs:

- [Grid](design-axes-grid.md): axis titles, grid and axis lines, and the Y-axis range.
- [X Ticks](design-axes-x-ticks.md): X-axis tick labels and their format.
- [Y Ticks](design-axes-y-ticks.md): Y-axis tick labels, their format and spacing.

Both tick tabs can use the custom formats described below.

---

## Custom number and date formats

Choose **Custom…** in the X-axis **Tick Format** or Y-axis **Number Format** menu, then enter a format string in the field that appears. The format changes the labels shown on the chart; it does not change the values in the table.

### Number formats

Number formats use [d3-format](https://github.com/d3/d3-format) notation. The number after the period sets the number of decimal places, and `,` adds thousands separators.

| Format | Example result | Use |
|---|---|---|
| `.0f` | `1235` | Whole numbers |
| `,.2f` | `1,234.50` | Thousands separator and two decimals |
| `.1%` | `45.6%` | Percentage with one decimal |
| `$,.2f` | `$1,234.50` | Currency with two decimals |
| `.2e` | `1.23e+4` | Scientific notation |

You can add text separately with the **Suffix** field. For example, use `,.0f` as the format and ` km` as the suffix to display `1,235 km`.

### Date formats

When the X-axis labels are recognized as dates, the X-axis menu changes to date presets. Choose **Custom…** and use [d3-time-format](https://github.com/d3/d3-time-format) directives:

| Format | Example result | Use |
|---|---|---|
| `%Y-%m-%d` | `2024-01-15` | ISO-style date |
| `%d %b %Y` | `15 Jan 2024` | Day, short month, and year |
| `%B %Y` | `January 2024` | Full month and year |
| `%b %d` | `Jan 15` | Short month and day |
| `%H:%M` | `14:30` | Hours and minutes |
| `%Y` | `2024` | Year only |

Common date directives are `%Y` for a four-digit year, `%m` for a two-digit month, `%d` for a two-digit day, `%b` for a short month name, `%B` for a full month name, `%H` for a 24-hour hour, and `%M` for minutes. The displayed month and day names follow the chart's **Output Locale** setting on [Design → Layout](design-layout.md#chart).

Date formatting applies to the X axis only. The Y axis contains numeric chart values and uses number formats.
