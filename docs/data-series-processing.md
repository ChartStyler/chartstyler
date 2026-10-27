---
layout: default
title: Processing
parent: Series
grand_parent: Data
nav_order: 3
---

# Data → Series → Processing

Use **Processing** to control how numbers are read, and to check the data that will be used for the chart.

---

## Decimal Separator

The **Decimal Separator** setting tells ChartStyler how to read numbers that use a decimal comma or decimal period. It affects how values are interpreted for the chart; it does not change the text stored in the InDesign table.

- **Auto**: ChartStyler examines the loaded numeric values and chooses the separator that appears most consistently. For example, `1,25` is read as 1.25 and `1.25` is read as 1.25. When there is not enough information to decide, it defaults to a decimal period.
- **Period**: use this for numbers such as `1,234.56`, where the period is the decimal separator and the comma separates thousands.
- **Comma**: use this for numbers such as `1.234,56`, where the comma is the decimal separator and the period separates thousands.

The setting is especially important when a table contains values with both a comma and a period. Choose the convention used by your data. If the preview or chart values look wrong, try the other setting or check that the values use one consistent number format.

The decimal separator setting controls numeric input only. It does not control the language of chart labels, dates, or axis display formatting; for that, see **Output Locale** on [Design → Layout](design-layout.md#chart).

> **Tip:** Use the same number format throughout a CSV file or InDesign table. For example, do not mix `1,234.56` and `1.234,56` in the same set of values unless you select a format that matches the data you want ChartStyler to read.

---

## Preview

The preview shows the series data exactly as it will be used for the chart, after the **Select**, **Adjust** and decimal separator settings are applied. Click **↻** to reload it.
