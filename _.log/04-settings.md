---
title: "Settings"
title_category: ".log"
permalink: /.log/settings/
excerpt: ".log JetBrains IDE Plugin Settings"
modified: 2025-01-04T19:00:00+02:00
---

## Customizing Color Scheme

Syntax highlighting Color Scheme of files opened with **.log plugin** can be customized to match any personal preferences.
To set custom colors/styles for log file elements (i.e. timestamps, log levels, message constructs):

1. Open the **Color Scheme** Settings:
- Navigate to **Settings** > **Editor** > **Color Scheme** > **File Types**.
- Select **Log Files** from the list of file types.

2. Adjust Specific Colors for Log Elements:
- In the **Logs** color scheme settings, you’ll see options for various log elements such as:
  - Log Levels (e.g., INFO, WARN, ERROR)
  - Timestamps, Category, Context id...
  - ANSI Color Codes (foreground & background color only)
- For each element foreground, background and font style (bold, italic, underline) can be customized. For ANSI codes only foreground and background colors are relevant.
- Click **Apply** and **OK** to save your changes. Changes will apply immediately.

![Log Color Scheme Settings](/assets/images/log/ss-log-settings-color-scheme.png)

## File Type Association

By default, **.log plugin** configured to support log file name patterns: `*.log;*.err;*.out;*.log.txt`.
To associate additional log file name patterns, to be viewed by **.log plugin**, update File Type Settings:
1. **Find Action** dialog (`⌘+⇧+A | Ctrl+⇧+A`) → Search: **File Types** (or alternatively, **Settings** (`⌘+, | Ctrl+Alt+S`) → **File Types**)
2. Under **Recognized File Types** → **Logs** → add file name patterns

![Log File Type Settings](/assets/images/log/ss-log-settings-file-type.png)

## File Size Thresholds

To ensure responsive performance, JetBrains sets a file size threshold for in-memory content loading. 

1. **File Size Thresholds**: If a log file exceeds the default 20 MB limitation, it will be opened as a Large File, as such file will be paginated. Text search will be slower while disk IO is performed.
2. **Increase File Content Loading Threshold**:
- Go to **Help** > **Edit Custom Properties…** to open the `idea.properties` file.
- Set/Add the property `idea.max.content.load.filesize` to a higher value.
- Restart the IDE for the changes to take effect. 
- Example idea.properties:
```properties 
# defaults to 20MB (for IDEA 2024.2)
#idea.max.content.load.filesize=20000
# For example extend to 50MB
idea.max.content.load.filesize=50000
```

**Note**: Currently, Log files opened as Large Files as noted above, are not supported with Problem Inspections.
{: .notice--info}

**Note**: If performance issues encountered, [please report](/.log/view-and-navigate/#submitting-issues--feature-requests) the details including file size, typical log line length, typical log snippet and preferably also host CPU/memory specs
{: .notice--warning}
