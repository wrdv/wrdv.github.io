---
title: "Quick-Start"
title_category: ".log"
permalink: /.log/
excerpt: "Quick introduction on how to use and install .log JetBrains IDE Plugin"
modified: 2026-07-07T22:30:00+03:00
---

[.log IntelliJ Plugin](https://plugins.jetbrains.com/plugin/25828--log) adds syntax highlighting and navigation features for log files and console output in JetBrains IDEs, similar to how source code files are treated.

{% comment %}{% include toc %}{% endcomment %}

## View

Open log files by either:
- Drag & Drop
- File Open Action: **Find Action** (`Cmd+Shift+A | Ctrl+Shift+A`) -> **Open...**
  - or Menu: **File** -> **Open...**

If the viewed file is not recognized as a `.log` file, configure file type association:
1. **Find Action** (`Cmd+Shift+A | Ctrl+Shift+A`) -> Search: **File Types**
2. or **Settings** (`Cmd+, | Ctrl+Alt+S`) -> **File Types**
3. Under **Recognized File Types** -> **Logs**: add file name patterns

**.log** features also apply to console output in Run/Debug configurations, Build tool windows, Terminal, and Services view. Structured JSON console logs can also be auto-rendered into a more readable one-line format while keeping the raw JSON accessible from the console UI. See [Console Log Support](/.log/console-log-support/) for details. For detailed information on log file features, see [Log Files Support](/.log/log-files/).

## Navigate
- Open hyperlinks in log files with `Cmd+B | Ctrl+B` or click
  - Hyperlinks are supported for file paths, URIs/URLs, and project resources. Navigation from log categories and stack traces is currently supported for Java/JVM only.
- Prev/Next problem navigation: `F2` / `Cmd+F2 | Shift+F2`
  - View all problems in **Problems** tool window: `Cmd+6 | Alt+6`

## Install
- On IDEA menu: **Settings** (`Cmd+, | Ctrl+Alt+S`) -> **Plugins** -> **Marketplace** -> Search: `.log` -> **Install**
- There is a 30-day free trial period. **.log plugin** licenses are available on the [JetBrains .log purchase page](https://plugins.jetbrains.com/plugin/25828--log/pricing)

## Submitting Issues & Feature Requests

Please submit feature requests and issues on the [.log GitHub issue tracker](https://github.com/wrdv/.log-issues/issues) or the [JetBrains .log plugin reviews page](https://plugins.jetbrains.com/plugin/25828--log/reviews)

If the issue concerns incorrect highlighting of log formats, please include:
- A snippet of the log file that reproduces the issue
- Which elements are not highlighted correctly, such as the log level or timestamp

If performance issues are encountered, please report:
- file size, typical log line length, sample log snippet. host CPU/memory specs could be helpful.
