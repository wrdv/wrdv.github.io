---
title: "Quick-Start"
permalink: /testme/
excerpt: "Quick introduction on how to use and install TestMe IntelliJ IDEA Plugin"
modified: 2024-03-27T22:00:00+02:00
---

**TestMe IntelliJ Plugin** generates Unit Test boilerplate code, leaving the developer to add the Unit Test logic.

{% comment %}{% include toc %}{% endcomment %}

### Generating Unit Test

Navigate from IDEA menu: `Code` -> `TestMe...` (`Alt`+`Shift`+`Q`) -> select Unit Test template from the popup menu.

#### Currently available Unit Test Templates

- _Unit4_ + _Mockito_
- _Unit4_ + _PowerMock_
- _Unit5_ + _Mockito_
- _TestNG_ + _Mockito_
- _Groovy_ +_Unit4_ + _Mockito_
- _Spock_ + _Mockito_
- _Spock_ Parameterized tests+ _Mockito_
- _Specs2(Scala)_ + _Mockito_

\* _Groovy_ and _Scala_ templates will only be available if the matching Jetbrains Groovy/Scala plugins are installed in IDEA. Jetbrains Groovy plugin is bundled with IntelliJ OOB. Scala plugin requires installation 

![Generate new unit test](/assets/images/screencast/simple-use-case.gif)

#### Alternative Navigation paths

- `Code` -> `Generate...` (`Alt`+`Ins` ) -> `TestMe...` 
- `Navigate` -> `Test` (`Ctrl`+`Shift`+`T`) -> `TestMe...` 

### Installation

  1. On IDEA menu: `Preferences` (`Ctrl`+`Shift`+`S`) -> `Plugins` -> `Browse repositories...` -> Search: `TestMe` -> `Install Plugin`
  2. Restart IDEA.
