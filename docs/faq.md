---
layout: default
title: FAQ
nav_order: 6
---

# Frequently asked questions

---

## How do I edit the data when I use a CSV file as a data source?

The ChartStyler plugin itself has no possibility to edit the data when you use the CSV file as a data source. If you want to edit the data in InDesign itself then you have to use an InDesign table as a data source. You can create an InDesign table using a CSV file as input. See data options in [Data Source](data-source.md)

If you prefer to keep your chart data in the CSV file itself then you can modify the CSV file with a text editor or an application like [Modern CSV](https://www.moderncsv.com/) that is specifically designed to edit CSV files.

---

## How do I show numbers with a decimal comma in the panel?

You can always type numbers with either a comma or a dot (`12,5` or `12.5`). To also *show* them with a comma, open **Preferences** and set **Decimal separator in the panel** to **Comma**:

- When no document is open, click **Preferences** at the bottom of the ChartStyler panel.
- When a document is open, double-click the **?** button at the top right of the panel to show the About screen, and click **Preferences** at the bottom.

**Auto** follows the language of InDesign: a comma for, for example, German, French or Dutch InDesign, and a dot for English. If you use English InDesign with comma region settings, choose **Comma**. The setting is saved for you personally, not in your documents.

---

## How do I send a log file?

ChartStyler test versions write a log file that helps to find out what went wrong, for example after a crash. To send it:

1. In the Finder, choose **Go → Go to Folder…** (Cmd+Shift+G). The folder is in your hidden *Library* folder, so this is the easiest way to get there.
2. Paste this path and press Return:

   ```
   ~/Library/Application Support/Adobe/UXP/PluginsStorage/IDSN/21/External/2952dacf.test/PluginData
   ```

   `21` is the version number of InDesign 2026. For another InDesign version, go up one level from `IDSN` and open the folder with that version's number.
3. Send the files you find there:
   - `chartstyler-debug.log` — the current session.
   - `chartstyler-debug-previous.log` — the previous session. **After a crash, this is the important one**: restarting InDesign starts a new log, and the session that crashed moves to this file.

The log contains technical details of what the plugin did, including the names of documents, tables and swatches you worked with. It doesn't contain the contents of your documents. Together the two files are at most about 10 MB.

---

## How do I turn debug logging on or off?

In test versions, logging is on. To turn it off (or back on):

1. Quit InDesign.
2. In the Finder, choose **Go → Go to Folder…** (Cmd+Shift+G) and open:

   ```
   ~/Library/Application Support/Adobe/UXP/Plugins/External/2952dacf.test_1.0.0/src
   ```

   The last part (`_1.0.0`) is the plugin version and changes with updates.
3. Open `debug-settings.js` in a plain-text editor (for example TextEdit, in plain-text mode) and change:
   - `logLevel: "DEBUG"` to `logLevel: ""` — turns all debug logging off, including the log file.
   - or only `logToFile: true` to `logToFile: false` — stops writing the log file.
4. Save the file and start InDesign again.

Installing an update of the plugin replaces this file, so logging is on again after an update.
