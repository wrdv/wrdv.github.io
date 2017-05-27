---
title: "Features"
permalink: /testme/features/
excerpt: "Overview of TestMe IntelliJ IDEA Plugin main features"
modified: 2017-05-27T15:00:00+02:00
---
### Feature list
- Auto generate _Java_ or _Groovy_ test class
- Generate Mocks for tested class's non-primitive fields
- Support _Mockito_ as a Mock framework
- Support _JUnit4_ , _JUnit5_ & _Spock_
- Generate Test methods for each accessible non-private method, excluding setters/getters
- Generate default input parameters for tested methods
- Generate test result assertion expression
- Supported target tested class language:  _Java_ , _Groovy_.

### Test parameters generation

Default values are auto generated for the tested methods parameters. Currently, this behaviour is not configurable. _Groovy_ tests generators are more robust in a sense that map constructors can be used (when applicable) to initialize objects with setters inline.
This is not supported yet for _Java_ test generators, since assignment to local variables for initialization of test parameters complicates the test generation template.
Personally, I would always recommend preferring _Groovy_ over _Java_ when it comes to unit testing. If you haven't transitioned yet to _Groovy_ as your test code language of choice - now is a good time start :)

### TestMe motto and current shortcomings

_TestMe IJ Plugin_ aims at generating as much Unit Test boilerplate as possible. The project still lacks some maturity level. You can further read about those dilemmas in [this blog post]({{ "/blog/testme/first-release" | absolute_url }})

[Sumbit a new Future Request on the project forum]({{ "/forum#!/testme/" | absolute_url }})
