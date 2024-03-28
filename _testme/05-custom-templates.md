---
title: "Custom Templates"
permalink: /testme/custom-templates/
excerpt: "TestMe IntelliJ IDEA Plugin Custom Test Templates"
modified: 2022-02-06T22:00:00+02:00
---

Custom test generation templates can be defined in IDEA Settings/Preferences
menu: `File` -> `Settings...` (`Ctrl`+`Alt`+`S` / `Cmd`+`,`) -> `TestMe` -> `TestMe Templates`

![TestMe Settings](/assets/images/testme-settings-templates.png)

Test generation templates are based on [Velocity templates](https://velocity.apache.org/engine/1.7/vtl-reference.html) engine.
Existing, OOB ( out of the box ) test generation templates cannot be modified but they can be viewed and cloned. The cloned templates can be edited.
Saved custom test templates will immediately become available for selection from TestMe test generation popup (`Alt`+`Shift`+`Q` / `Option` + `Shift` + `Q`).

### Defining custom templates

Available options to mange custom templates:

- Clone and modify existing template
- Create a new template from scratch
- Delete a custom template
- Define a shared code file, on the _Includes_ tab, to be reused between templates

Target test subject class introspection is supported for Java, Groovy & Scala only (if Jetbrains Groovy/Scala plugins are installed and enabled),
but test classes can be generated for any language by specifying the required extension on the newly defined custom template.

**Tip:** You might notice on the OOB templates - commented out import statements - these statements will be generated as un-commented code on the test class.
At least for supported languages - Java, Groovy, Scala. They are commented out on the test template as a workaround since typically imports are optimized
automatically post test generation.
Sometimes its handy to get static imports of mock or assertion library ready to be used even if newly generated test code did not make any use of it.
{: .notice--info}

### Velocity Template context

Custom variables/objects are injected and available at runtime from the [Velocity template](https://velocity.apache.org/engine/1.7/vtl-reference.html).
Following variable can be used with Velocity's $ operator:

| Variable              | Description                                                                                                                                                                           |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TestBuilder           | Instance of [com.weirddev.testme.intellij.template.context.TestBuilder](/testme/javadoc/com/weirddev/testme/intellij/template/context/TestBuilder.html)                               |
| MockitoMockBuilder    | Instance of [com.weirddev.testme.intellij.template.context.MockitoMockBuilder](/testme/javadoc/com/weirddev/testme/intellij/template/context/MockitoMockBuilder.html)                 |
| PowerMockBuilder      | Instance of [com.weirddev.testme.intellij.template.context.PowerMockBuilder](/testme/javadoc/com/weirddev/testme/intellij/template/context/PowerMockBuilder.html)                     |
| TestSubjectUtils      | Instance of [com.weirddev.testme.intellij.template.context.TestSubjectInspector](/testme/javadoc/com/weirddev/testme/intellij/template/context/TestSubjectInspector.html)             |
| StringUtils           | Instance of [com.weirddev.testme.intellij.template.context.StringUtils](/testme/javadoc/com/weirddev/testme/intellij/template/context/StringUtils.html)                               |
| TESTED_CLASS          | Instance of [com.weirddev.testme.intellij.template.context.Type](/testme/javadoc/com/weirddev/testme/intellij/template/context/Type.html) - representing Class of target test subject |
| CLASS_NAME            | Test subject class name                                                                                                                                                               |
| PACKAGE_NAME          | Test subject package name                                                                                                                                                             |
| TESTED_CLASS_LANGUAGE | Test subject class name                                                                                                                                                               |
| MAX_RECURSION_DEPTH   | Configured max recursion depth for object graph introspection                                                                                                                         |
| MONTH_NAME_EN         | Current English Month name. format MMMM                                                                                                                                               |
| DAY_NUMERIC           | Current Day of month for numeric calculations. i.e. if today is January the 2nd then DAY_NUMERIC is 2                                                                                 |
| HOUR_NUMERIC          | Current Hour for numeric calculations. i.e. if the current time is 09:45 then HOUR_NUMERIC is 9                                                                                       |
| MINUTE_NUMERIC        | Current Minute for numeric calculations. i.e. if the current time is 09:05 then MINUTE_NUMERIC is 5                                                                                   |
| SECOND_NUMERIC        | Current Second for numeric calculations. i.e. if the current time is 09:15:05 then SECOND_NUMERIC is 5                                                                                |

