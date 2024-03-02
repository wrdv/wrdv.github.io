---
title: "Settings"
permalink: /testme/settings/
excerpt: "TestMe IntelliJ IDEA Plugin Settings and Configuration"
modified: 2018-08-22T22:00:00+02:00
---

Some aspects of the test generation behavior can be controlled from IDEA Settings/Preferences menu: `File` -> `Settings...` (`Ctrl`+`Alt`+`S`) -> `Other Settings` -> `TestMe`

![TestMe Settings](/assets/images/testme-settings.png)

### Configurable options

##### Generate tests for inherited methods

When set, TestMe will generate tests for inherited methods
Default:checked

##### Reformat code

When set, generated test will be reformatted according to relevant language formatting settings in IDEA.
IDEA code formatting settings can be found in this settings form under `Editor` -> `Code Style`
Default:checked

##### Replace Fully Qualified Names (FQN) with imports

When set, fully qualified class names will be replaced with import statements where possible in generated test
Default:checked

##### Optimize imports

Optimize imports for generated test. This option just trigger IDEA optimize imports action (`Ctrl`+`Alt`+`O`) for the newly generated test class.
Default:checked