---
title: "Quick-Start"
title_category: ".log"
permalink: /.log/
excerpt: "Quick introduction on how to use and install .log JetBrains IDE Plugin"
modified: 2024-11-10T22:00:00+02:00
---

[.log IntelliJ Plugin](https://plugins.jetbrains.com/plugin/25828--log) supports code language features when viewing log files, with syntax highlighting and navigation. 

{% comment %}{% include toc %}{% endcomment %}

## View

Open log files by either:
- Drag & Drop
- File Open Action: **Find Action** (`⌘+⇧+A | Ctrl+⇧+A`) → **Open...**
  - or Menu: **File** → **Open...**
 
If the viewed file is not recognized as a .log file, configure file type association:
1. **Find Action** (`⌘+⇧+A | Ctrl+⇧+A`) → Search: **File Types**
   2. or **Settings** (`⌘+, | Ctrl+Alt+S`) → **File Types**
2. under **Recognized File Types** → **Logs** : add file name patterns 

## Navigate
- Open hyperlinks in log files with `⌘+B | Ctrl+B` or click 
  - Hyperlinks supported for File paths, URIs/URLs and project resources. Note: hyperlink navigation from log categories and stack traces - currently supported for Java/JVM only.
- Prev/Next problem navigation: `F2`/`⌘+F2 | ⇧+F2`
  - View all problems in **Problems** tool window: `⌘+6 | Alt+6`

## Install
- On IDEA menu: **Settings** (`⌘+, | Ctrl+Alt+S`) → **Plugins** → **Marketplace** → Search: `.log` → **Install**
- There's a 30 Days free trial period. **.log plugin** license is available for purchase on [JetBrains .log purchase page](https://plugins.jetbrains.com/plugin/25828--log/pricing)
