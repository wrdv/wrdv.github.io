---
title: "Features"
permalink: /testme/features/
excerpt: "Overview of TestMe IntelliJ IDEA Plugin main features"
modified: 2017-01-29T22:00:00+02:00
---
#### Feature list
- Generate Mocks for tested class's non-primitive fields
- Support Mockito as a Mock framework
- Support JUnit4 and JUnit5
- Generate Test methods for each accessible non-private method, excluding setters/getters
- Generate dummy input parameters for tested method
- Generate test result assertion expression


#### TestMe motto and current shortcomings

**TestMe IJ Plugin** aims at generating as much Unit Test boilerplate as possible, any code that is based on the tested class signature (white box unit testing) and does not involve logic related to internal implementation - should be generated automatically.
This project is still making it's first steps towards this goal and many use cases are still not covered. To some level, the code generator is opinionated as to how a typical test class is structured and assumes that a testable class follows some basic principles.
Furthermore, the generated test code adheres to the limitations of the Mocking framework being used (currently, only Mockito is supported). As a result, on some use cases, the generated code might not even pass compilation.
On some cases this is a known limitation taken into account, where the added value of having an auto generated base code as a starting point - overcomes the effort of handling the compilation error.
On other cases, the project simply hasn't gained the maturity level to cover those use cases yet.
If you think you encountered a bug, or a use case where things can be handled better - please report it. Reported issues will typically be prioritized higher than planned features on the project road map.
Same goes to feature requests, I've got no idea what you want if you wont tell me about it :smile:.

Issue tracking is managed at [GitHub Project Issues](https://github.com/wrdv/testme-idea/issues).

[Submit a new issue](https://github.com/wrdv/testme-idea/issues/new){: .btn .btn--info}