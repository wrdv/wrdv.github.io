---
title: "View & Navigate"
title_category: ".log"
permalink: /.log/view-and-navigate/
excerpt: ".log JetBrains IDE Plugin main features"
modified: 2024-11-10T22:00:00+02:00
---

## Syntax Highlighting

**.log** automatically detects and highlights common log formats, including timestamps, log levels, categories, stack traces, log message constructs (numbers, measures, strings, value literals), and ANSI rendering instructions (Note: When scrolling rapidly, ANSI-codes highlighting may lag due to asynchronous rendering, designed to maintain UI responsiveness).

**Note:** In some cases, some log elements may not be highlighted as expected due to difficulties in reverse engineering human-readable log output to machine instructions. Typically, the impact is negligible. Regardless, please report anomalies. In some cases, rendering syntax can still be improved.
{: .notice--warning}

For any unrecognized log formats or highlighting inconsistencies, please [submit an issue with a log sample](#submitting-issues--feature-requests).

## Log events time range
  
log file name display, on project view, or file tab, will include the time range of its log entries. date format will abbreviate and omit  year, month,day - if those match current date

## Navigation - Hyperlinks

Some log elements are converted to hyperlinks:
  - URIs/URLs: Open URLs directly from the log.
  - File Paths
  - Log Categories & Stack Traces (Java/JVM support only for now).

Open Hyperlinks - with Keyboard Shortcut: `Cmd + B | Ctrl + B` or a Click

**Note:** Code navigation may not always work as expected. on some cases it's not feasible to locate project resources without additional hints. Navigation to code is supported for JVM-based languages only or now (support planned for additional languages/frameworks). regardless, please report any issue, so we can improve the navigation experience.
{: .notice--warning}

## Navigation - Problem Inspections

Opened log files are inspected for Errors and Warnings - each of those are
- highlighted in the editor
- reflected as a heatmap on the right side of the editor
- listed in the Problems Tool Window.

1. Navigate to Next/Previous Problem - with keyboard shortcut `F2` / `⌘+F2 | ⇧+F2`
2. View All Problems in the Problems Tool Window - Keyboard Shortcut: `⌘+6 | Alt+6`

By default, only **Errors** are cycled through with problem navigation. To include **Warnings**:
1. Hover over the error/warning counter in the top right corner of the editor.
2. Click on the three-dot menu and adjust the settings.
3. Alternatively, go to **Settings** > **Editor** > **Code Editing** > **Error highlighting** or use **Find Actions** (`⌘+⇧+A | Ctrl+⇧+A`) dialog.

**Note:** There is a cap on the maximum reported problems for performance. If there's a need to increase this cap, please [report an issue](#submitting-issues--feature-requests), so we can consider adding a setting for that.
{: .notice--info}

## Planned Features

Following features are planned for 2024/2025:

1. Code Navigation - Support additional languages/frameworks
2. Support console logs.
3. Support remote log files

Reported feature requests will be prioritized over planned roadmap features.

## Submitting Issues & Feature Requests

Please submit feature requests & issues on [JetBrains .log plugin reviews page](https://plugins.jetbrains.com/plugin/25828--log/reviews)

If the issue concerns incorrect highlighting of log formats, please include:
- A snippet of the log file that reproduces the issue.
- Specify the elements (e.g., log level, timestamp) that are not highlighted correctly.

