---
title: "Settings"
title_category: ".log"
permalink: /.log/settings/
excerpt: ".log JetBrains IDE Plugin Settings"
modified: 2024-11-10T22:00:00+02:00
---

## File Type Association

By default, **.log plugin** configured to support log file name patterns: `*.log;*.err;*.out;*.log.txt`.
To associate additional log file name patterns, to be viewed by **.log plugin**, update File Type Settings:
1. **Find Action** dialog (`⌘+⇧+A | Ctrl+⇧+A`) → Search: **File Types** (or alternatively, **Settings** (`⌘+, | Ctrl+Alt+S`) → **File Types**)
2. Under **Recognized File Types** → **Logs** → add file name patterns


## Supported File Size

To ensure responsive performance, JetBrains sets a file size limitation. Since viewing log files typically consumes less resources then code source files, this limitation can be extended without significant performance impact. 

1. **File Size Limitation**: If a log file exceeds the default 20 MB limitation, it will not be supported and a notification will appear at the top of the editor.
2. **Increase File Size Limit**:
- Go to **Help** > **Edit Custom Properties…** to open the `idea.properties` file.
- Set/Add the property `idea.max.content.load.filesize` to a higher value.
- Restart the IDE for the changes to take effect. 
- Example idea.properties:
```
#---------------------------------------------------------------------  
# Maximum file size (in KiB) the IDE is able to open.  
#---------------------------------------------------------------------  
# defaults to 20MB (for IDEA 2024.2)
#idea.max.content.load.filesize=20000
# For example extend to 100MB
idea.max.content.load.filesize=100000
```

**Note**: If performance issues arise, [please report](/.log/view-and-navigate/#submitting-issues--feature-requests) the details including file size, typical log line length, typical log snippet and preferably also host CPU/memory specs
{: .notice--warning}

## Customizing Color Scheme

Syntax highlighting Color Scheme of files opened with **.log plugin** can be customized to match any personal preferences.
To set custom colors/styles for log file elements (i.e. timestamps, log levels, message constructs):

1. Open the **Color Scheme** Settings:
- Navigate to **Settings** > **Editor** > **Color Scheme** > **File Types**.
- Select **Log Files** from the list of file types.

2. Adjust Specific Colors for Log Elements:
- In the **Logs** color scheme settings, you’ll see options for various log elements such as:
  - Timestamps
  - Log Levels (e.g., INFO, WARN, ERROR)
  - Text and Background Colors
- Customize each element by selecting it and adjusting the foreground and background colors with the color picker. reflected in instant preview.
- Click **Apply** and **OK** to save your changes. Changes will apply immediately.

### Tips for Color Customization

- **Dark and Light Themes**: Adjust colors separately for light and dark themes by switching the theme and setting colors for each.
- **ANSI Color Codes**: Consider adjusting ANSI Color settings as well to complement your theme. Please note that .log color settings for log level, timestamp and few other elements may take precedence over ANSI color codes. if you prefer other behavior, please [report the issue](/.log/view-and-navigate/#submitting-issues--feature-requests).
