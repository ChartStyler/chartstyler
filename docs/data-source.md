---
layout: default
title: Source
parent: Data
nav_order: 1
---

# Data → Source

Use the **Source** tab to choose where the chart data comes from. ChartStyler can use an InDesign table in the document, or a linked CSV file on disk.

---

## Select Data Source

The dropdown lists the data sources available in the document: InDesign tables created with ChartStyler or imported from CSV files, and linked CSV files. Select the one that contains your chart data. When you select a table, ChartStyler shows its size and, for CSV imports, the source file and import time. Click **⌖** to select the table in the InDesign document.

- **Table Name**: label used to identify the table in the dropdown. Click **Rename** to change it. Several charts can use the same table.
- **↻ Refresh from Source File…**: reloads the data from the CSV file the table was imported from. See [Refresh CSV data](#refresh-csv-data).

To change the appearance of specific data points or bars, for example to highlight selected values, use **Data → Series → Groups**. See [Groups](data-series-groups.md) for details.

---

## Add Data Source

### From InDesign Table

The chart data is stored in an InDesign table in the document, where you can edit it directly.

- **+ New Blank Table**: enter a table name and the number of rows and columns to place an empty InDesign table at the current text cursor. You can then type the values, or copy and paste them from Excel or from an HTML table in your browser. See description of how to to that in [Getting Started](getting-started.md).
- **+ Import CSV as Table**: choose a CSV file. A new InDesign table is created and the data is placed in it automatically.

> **Tip:** Select the destination cells in the InDesign table, then copy and paste a range from Excel or cells from an HTML table in your browser. InDesign fills the selected table cells with the pasted values.

A table used as a data source is part of the document. If it shouldn't print, place it outside the page area or on a non-printing layer.

### From CSV File

- **+ Link CSV**: use a CSV file on disk directly as the data source, without creating a table. Edit the CSV file to change the data. This is practical for larger data sets. Keep the file available if you want to update the chart later.

---

## CSV file format

ChartStyler reads the complete contents of the selected file and places each value into an InDesign table cell. The file should contain one row of data per line. The first row is not treated specially during import; use the **Series → Select** tab to tell ChartStyler which row contains series names and which rows contain data.

Comma-separated files are the usual choice, but ChartStyler can also detect tab-, pipe-, and semicolon-separated files. Keep the same separator throughout the file. Values that contain the separator, a line break, or quotation marks should be enclosed in double quotation marks, as in the example below. Empty cells are kept as empty table cells, and spaces around values are removed.

```csv
Month,Sales,Costs
January,1250,800
February,1380,820
March,1495,910
```

Save the file as UTF-8, preferably as UTF-8 without a byte-order mark, so that accented characters and other non-English text are imported correctly. ChartStyler does not convert CSV values to numbers while importing; values remain text until the chart data is read, using the **Decimal Separator** setting on the [Series → Processing](data-series-processing.md) tab. A malformed row or invalid CSV quoting stops the import and displays an error.

---

## Refresh CSV data

When the selected table was imported from a CSV file, click **↻ Refresh from Source File…** to load the latest data from that CSV. ChartStyler normally remembers the file and opens it automatically. If the file was moved or is no longer available, you will be asked to choose the CSV file again.

Refreshing replaces the table contents with the contents of the CSV file. ChartStyler shows the current and new table sizes and asks you to confirm before making the change. Any rows or columns that were added or removed in the CSV are also reflected in the InDesign table. The table itself keeps its identity, so charts that use it remain connected.

This option is only available for tables imported from CSV files. It is not shown for tables created with **+ New Blank Table**.
