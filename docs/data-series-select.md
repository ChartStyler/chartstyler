---
layout: default
title: Select
parent: Series
grand_parent: Data
nav_order: 1
---

# Data → Series → Select

Use **Select** to tell ChartStyler which parts of the table are labels, series names and values.

- **Data Orientation**: choose **Columns** when each column contains a series, or **Rows** when each row contains a series.
- **Label Column / Label Row**: the column or row containing the category labels, such as months or product names. These labels appear along the X axis, or as slice names in a pie or donut chart.
- **Series Name Row / Series Name Column**: the row or column containing the name of each series. These names appear in the legend.
- **Data Start Row**: the first row that contains values. Rows above it, such as the header row, are not plotted.
- **Data Start Column**: the first column that contains values. Columns to its left, such as the label column, are not plotted.

All index values are 1-based. With the usual layout, row 1 contains the series names, column 1 contains the category labels, and chart values start at row 2 and column 2.

---

## Source Table Preview

The preview shows the table with each cell coloured by how it is used: series values in light blue, series names in dark blue, and category labels in yellow. Click **↻** to reload it after changing the table.

---

## Example: series in columns

This is the usual table layout. Each data column becomes one chart series:

|   | A | B | C |
|---|---|---|---|
| 1 | Month | Sales | Costs |
| 2 | January | 1250 | 800 |
| 3 | February | 1380 | 820 |
| 4 | March | 1495 | 910 |

Use these settings:

| Setting | Value | What it does |
|---|---:|---|
| **Data Orientation** | Columns | Reads each data column as a series. |
| **Label Column** | 1 | Uses column A for the category labels. |
| **Series Name Row** | 1 | Uses row 1 for the series names, `Sales` and `Costs`. |
| **Data Start Row** | 2 | Starts values below the series-name row. |
| **Data Start Column** | 2 | Starts values to the right of the label column. |

ChartStyler produces two series: **Sales** = 1250, 1380, 1495 and **Costs** = 800, 820, 910. The category labels are January, February, and March.

---

## Example: series in rows

Use **Rows** when each row, rather than each column, is a series:

|   | A | B | C | D |
|---|---|---|---|---|
| 1 |   | January | February | March |
| 2 | Sales | 1250 | 1380 | 1495 |
| 3 | Costs | 800 | 820 | 910 |

Use these settings:

| Setting | Value | What it does |
|---|---:|---|
| **Data Orientation** | Rows | Reads each data row as a series. |
| **Label Row** | 1 | Uses row 1 for the category labels. |
| **Series Name Column** | 1 | Uses column A for the series names, `Sales` and `Costs`. |
| **Data Start Row** | 2 | Starts values below the label row. |
| **Data Start Column** | 2 | Starts values to the right of the series-name column. |

ChartStyler produces the same two series as in the first example. The settings tell ChartStyler which cells are labels and names, so those cells are not treated as chart values.
