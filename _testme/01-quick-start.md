---
title: "Quick-Start"
permalink: /testme/
excerpt: "Quick introduction on how to use and install TestMe IntelliJ IDEA Plugin"
modified: 2017-02-20T21:00:00+02:00
---

**TestMe IntelliJ Plugin** generates Unit Test boilerplate code, leaving the developer to add the Unit Test logic.

{% comment %}{% include toc %}{% endcomment %}

### Generating Unit Test (or - Show Me The Money!)

Navigate from IDEA menu: `Code` -> `TestMe...` (`Alt`+`Shift`+`Q`) -> select Unit Test template from the popup menu.

#### Currently available Unit Test Templates

- _Unit4_ + _Mockito_
- _Unit5_ + _Mockito_
- _Groovy_ +_Unit4_ + _Mockito_
- _Spock_ + _Mockito_

![Generate new unit test](/assets/images/screencast/simple-use-case.gif)

#### Alternative Navigation paths

- `Code` -> `Generate...` (`Alt`+`Ins` ) -> `TestMe...` 
- `Navigate` -> `Test` (`Ctrl`+`Shift`+`T`) -> `TestMe...` 

### Installation

As any IJ IDEA plugin: 

1. From IDEA menu: `Preferences` (`Ctrl`+`Shift`+`S`) -> `Plugins` -> `Browse repositories...` -> Search: `TestMe` -> `Install Plugin`
2. Restart IDEA.

### Version Compatibility

TestMe plugin is compatible with IntelliJ IDEA versions 14.x, 15.x, 2016.x, 2017.x. The plugin was not tested on other versions.
