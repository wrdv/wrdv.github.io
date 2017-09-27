---
title: "Features"
permalink: /testme/features/
excerpt: "Overview of TestMe IntelliJ IDEA Plugin main features"
modified: 2017-09-27T15:00:00+02:00
---
### Feature list
- Auto generate _Java_ or _Groovy_ test class
- Generate Mocks for tested class's non-primitive fields
- Support _Mockito_ as a Mock framework
- Support _JUnit4_, _JUnit5_, _TestNG_ & _Spock_ frameworks
- Generate Test methods for each accessible non-private method, excluding setters/getters
- Generate default input parameters for tested methods
- Generate test result assertion expression
- Supported target tested class language:  _Java_ , _Groovy_.

### Test parameters generation

Default values are auto generated for the tested methods parameters. Currently, this behaviour is not configurable. _Groovy_ tests generators are more robust in a sense that map constructors can be used, when applicable, to initialize objects with setters inline.
Such matching feature is not supported yet for _Java_ test generators, since assignment to local variables for initialization of test parameters complicates the test generation template.
Personally, I would always recommend preferring _Groovy_ over _Java_ when it comes to unit testing. If you haven't transitioned yet to _Groovy_ as your test code language of choice - now is a good time start :)

**Tip:** Generated test method call line can get very long depending on the depth level of nested objects passed to the tested method. Set the max line limit in IntelliJ Code Style configuration:
`Preferences` (`Ctrl`+`Shift`+`S`) -> `Editor` -> `Code Style` -> `Java` or `Groovy` -> set `Right margin (columns)` and check `Ensure right margin is not exceeded`.
Please note these settings will effect not just the test code generation. Currently its not possible to control the max line length for generated test code only.
{: .notice--info}

### Test class mocks generation

Mocks are generated for non primitives/non wrapper types classes. Currently, only _Mockito_ is supported as the mock framework.
There's some difficulty in identifying which class member dependency should be mocked. On some use cases the answer to this question may be controversial. There's still some work to be done here.   

**Tip:** By default, Mockito mocks will not be generated for final types. To turn that option on, as specified in [these Mockito instructions](https://github.com/mockito/mockito/wiki/What%27s-new-in-Mockito-2#mock-the-unmockable-opt-in-mocking-of-final-classesmethods),
create a file in project resources with the path uri - /mockito-extensions/org.mockito.plugins.MockMaker. The file should contain the line: mock-maker-inline.
{: .notice--info}

### TestMe motto and current shortcomings

_TestMe IJ Plugin_ aims at generating as much Unit Test boilerplate as possible. The project still lacks some maturity level. You can further read about those dilemmas in [this blog post]({{ "/blog/testme/first-release" | absolute_url }})

[Sumbit a new Future Request on the project forum]({{ "/forum#!/testme/" | absolute_url }})
