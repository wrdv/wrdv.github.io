---
title: "Quick-Start"
permalink: /testme/quick-start/
excerpt: "Quick introduction on how to use and install TestMe IntelliJ IDEA Plugin"
modified: 2017-01-29T21:00:00+02:00
---

**TestMe IntelliJ Plugin** generates Unit Test boilerplate code, leaving the developer to add the Unit Test logic.

{% comment %}{% include toc %}{% endcomment %}

### Generating Unit Test (or - Show Me The Money!)

Navigate from IDEA menu: `Code` -> `TestMe...` (`Ctrl`+`Shift`+`Q`) -> select Unit Test template from the popup menu.

#### Currently available Unit Test Templates

- _Unit4 + Mockito_
- _Unit5 + Mockito_

![Generate new unit test](/assets/images/screencast/simple-use-case.gif)

#### Alternative Navigation paths

- `Code` -> `Generate...` (`Alt`+`Ins` ) -> `TestMe...` 
- `Navigate` -> `Test` (`Ctrl`+`Shift`+`T`) -> `TestMe...` 

### Installation

As any IJ IDEA plugin: 

1. From IDEA menu: `Preferences` (`Ctrl`+`Shift`+`S`) -> `Plugins` -> `Browse repositories...` -> Search: `TestMe` -> `Install Plugin`
{% comment %} 
- Manually:
  - Download the [latest release][latest-release] and install it manually using `Preferences` -> `Plugins` -> `Install plugin from disk...`
{% endcomment %}
2. Restart IDE.
