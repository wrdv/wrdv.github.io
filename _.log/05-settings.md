---
title: "Settings"
title_category: ".log"
permalink: /.log/settings/
excerpt: ".log JetBrains IDE Plugin Settings"
modified: 2026-07-07T22:30:00+03:00
---

## Customizing Color Scheme

Syntax highlighting color scheme for files opened with **.log plugin** can be customized to match personal preferences.
To set custom colors and styles for log file elements such as timestamps, log levels, and message constructs:

1. Open the **Color Scheme** settings:
- Navigate to **Settings** -> **Editor** -> **Color Scheme** -> **File Types**
- Select **Log Files** from the list of file types

2. Adjust specific colors for log elements:
- In the **Logs** color scheme settings, you will see options for various log elements such as:
  - Log Levels (for example INFO, WARN, ERROR)
  - Timestamps, Category, Context id
  - ANSI Color Codes (foreground and background only)
- For each element, foreground, background, and font style can be customized. For ANSI codes only foreground and background colors are relevant.
- Click **Apply** and **OK** to save your changes. Changes apply immediately.

![Log Color Scheme Settings](/assets/images/log/ss-log-settings-color-scheme.png)

## File Type Association

By default, **.log plugin** is configured to support these log file name patterns: `*.log;*.err;*.out;*.log.txt`.
To associate additional log file name patterns so they are viewed by **.log plugin**, update file type settings:

1. Open **Find Action** (`Cmd+Shift+A | Ctrl+Shift+A`) -> search for **File Types**
2. Or open **Settings** (`Cmd+, | Ctrl+Alt+S`) -> **File Types**
3. Under **Recognized File Types** -> **Logs** -> add file name patterns

![Log File Type Settings](/assets/images/log/ss-log-settings-file-type.png)

## ANSI Escape Codes

When a log file contains ANSI escape codes, **.log plugin** applies text styling according to those codes and hides the raw escape sequences for a cleaner view. Files opened with ANSI styling are **read-only**.

This behavior can be toggled per file when relevant - see [Display Transformation](/.log/log-files/#display-transformation).

## JSON Console Logs

JSON console-log destructuring does not currently have a dedicated persisted option under the Settings UI. The feature is controlled from the console itself and follows the runtime or session behavior described in [Console Output](/.log/console-log-support/#json-console-logs).

Destructured JSON output reuses the regular log highlighting pipeline and also adds a dedicated color-scheme entry for extra property names:

- **Logs** -> **Destructured JSON** -> **Extra Property Name**

Console-specific behavior such as raw JSON actions and performance-related line-length limits is documented on the [Console Output](/.log/console-log-support/#json-console-logs) page.

## File Size Thresholds

To ensure responsive performance, JetBrains IDE has a file size threshold for in-memory content loading.

When a log file exceeds this threshold (default 20 MB), it is opened as a **Large File** with pagination and large-file view optimization. The file is **read-only** in this mode. Text search may be slower while disk I/O is performed. On the other hand, file scrolling and overall UX may be more responsive.

**Note**: Problem inspections are not supported for log files opened as Large Files. See [Navigation - Problem Inspections](/.log/log-files/#navigation---problem-inspections) for details.
{: .notice--info}
