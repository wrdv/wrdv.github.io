---
title:  "TestMe -- Configuration hacks"
modified: 2018-23-07T22:30:00+02:00
categories:
  - TestMe
tags:
  - TestMe Plugin
  - Intellij IDEA
  - TestMe Plugin Configuration
  - Auto generate unit test code in Java, Groovy or Scala
  - generate Java or Groovy test mocks
  - IntelliJ - IDE Scripting Console
---

**Update - Aug 23, 2018:** Support for the following configurable properties have been removed since they are now configurable as an integral part of the [new Settings UI]({{ "/testme/settings/" | absolute_url }}) in release 2.0.0:
`testMe.style.replaceFqn`, `testMe.style.reformatCode`, `testMe.style.optimizeImports`.
{: .notice--info}


Release 1.7 added support for configurable properties to control some of [TestMe IJ IDEA Plugin]({{ "/testme/ " | absolute_url }}) behaviour. Well... sort of. The truth is that no configuration screens were introduced but now it's possible to hack the plugin via the *IDE Scripting Console*.


### Why a proper configuration screen was not added? 

Since the current UI is minimalistic and the test templates behaviour would be better controlled by a feature test template customization option the main functionality that is currently relevant for control by user configuration is the test generation engine behaviour.
Letting the user control that behaviour has some problematic implications on the future development an evolution of this plugin. some features that are related to the random test parameters generation behaviour for instance are not fully matured.
Users may want to turn off some of these features, since the user choice must be respected and persisted between IDE restarts ( otherwise users will really get annoyed...), this means that many users may blind to future improvements.
The aim here is to improve the plugin to a level where the resulted generated test code is a good fit for the required test code structure in 90% of the use cases, so only a few, quick adaptations, mainly in the test input/assertion values - will be required to complete the unit test development. 
Ideally, the plugin should provide an almost fully automated experience and "know what to do" rather than relay the user the tweak the configuration to get the desired results. 
If the current functionality is falling short, please raise an issue on the [project forum]({{ "/forum#!/testme/" | absolute_url }}).

### The compromised solution 

The built-in scripting/macro tool in IDEA comes handy here to provide a way to hack the configuration. This non standard approach, based on setting system properties at runtime with a script, is far from being user friendly, but is has some important advantages:
* The updated configuration is not persisted, so important features that should be improved in future versions are not ignored.    
* As an unofficial, internal configuration, users do not expect future support so much less potential disappointed here.   
* The script itself in the scripting console is persisted between IDEA restarts. no need to write or copy paste it again.
* Yes. admittedly. the development cost is also a consideration. :)


### TL;DR - How to hack TestMe Configuration
To change *TestMe IJ Plugin* configuration properties at runtime:

1. Paste this Groovy code listed below at the **_IDE Scripting Console_** (opened from IntelliJ **_Tools_** menu)
2. Select Groovy as the script Language
3. Un-comment ( Ctrl + / ) or update the relevant statement
4. Mark or place the cursor on the relevant statement and press Ctrl+Enter

``` groovy
/**
 * Test parameters generator feature. limit the maximum depth of recursive nested parameters initialization and recursion of tested class structure inspection.
 * Warning: raising this value above 9 may result in severe performance degradation during test generation, to a point where the IDE is not responsive for over a minute.
 * Valid values:1-20
 * Default:9
 */
System.properties.setProperty("testMe.generator.maxRecursionDepth", "9")//set default value

/**
 * Test parameters generator optimization. when true - heuristically identify and ignore unused properties by the tested method, so null is passed for constructor arguments that initialize unused properties. In case a Groovy map constructor used - property will not be initialized
 * Valid values:true,false
 * Default:true
 */
System.properties.setProperty("testMe.generator.ignoreUnusedProperties", "true")//set default value
//System.properties.setProperty("testMe.generator.ignoreUnusedProperties", "false")//set default value

/**
 * Test parameters generator feature.replace interface/abstract argument types with concrete types if exists in project. otherwise pass null.
 * Valid values:true,false
 * Default:true
 */
System.properties.setProperty("testMe.generator.replaceInterfaceParamsWithConcreteTypes", "true")//set default value
//System.properties.setProperty("testMe.generator.replaceInterfaceParamsWithConcreteTypes", "false")//set default value

/**
 * Test mocks generator feature. generate mocked method call response in case mocks that return a value are called by the tested method and the calling code is part of the tested method
 * Valid values:true,false
 * Default:true
 */

System.properties.setProperty("testMe.generator.stubMockMethodCallsReturnValues", "true")//set default value
//System.properties.setProperty("testMe.generator.stubMockMethodCallsReturnValues", "false")//set default value

/**
 * Test parameters generator feature. only relevant when replaceInterfaceParamsWithConcreteTypes is true.
 * If the number of concrete implementations found in project sources is over this limit - then Interface param will not be initialized. otherwise a random selection of the found concrete types will be used.
 * This ia a heuristic number, assuming too many implementations is an indicator to an interface that is too generic (i.e. comparator) - so an arbitrary implementation should not be selected in such case
 * Valid values:1-100
 * Default:2
 */
System.properties.setProperty("testMe.generator.maxNumOfConcreteCandidatesToReplaceInterfaceParam", "5")//set default value

/**
 * Test parameters generator optimization. Relevant for Groovy tests.
 * When the amount of a given type setters exceeds by this percentage value over of the number of arguments in the type constructor that has the maximum number of arguments - then a map constructor is used to initialize the type
 * Valid values:0-100
 * Default:50
 */
System.properties.setProperty("testMe.generator.minPercentOfExcessiveSettersToPreferMapCtor", "50")//set default value

/**
 * Relevant when shouldIgnoreUnusedProperties is true. When the minimum percentage of all interactions with constructed type are via setters/getters or direct property field read/assignment - then the type is considered as a 'data' bean,
 * so a null value is passed for any constructor argument that is bound to a field in the constructed type which is not used in the tested method. in case a map constructor being used - than the property will not be initialized.
 * Valid values:0-100
 * Default:66
 */
System.properties.setProperty("testMe.generator.minPercentOfInteractionWithPropertiesToTriggerConstructorOptimization", "66")//set default value
``` 
Happy coding :)
