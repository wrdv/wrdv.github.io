---
title:  "TestMe IntelliJ IDEA Plugin -- First Release"
modified: 2017-01-30T20:45:00+02:00
categories: 
  - TestMe
tags:
  - MVP
  - Intellij IDEA
---

First release of [TestMe IJ IDEA Plugin]({{ "/testme/quick-start/" | absolute_url }}) has just been uploaded to JetBrains plugins repository and is available for [installation]({{ "/testme/quick-start/" | absolute_url }}) from withing IntelliJ IDEA.

## When to release?

When is it about time to release the first version to be made publicly available? What features should be included in this first release? Typically you would like go to release as soon as possible.
When it's out on the open, you might get feedback from actual users, you'll gain knowledge of what features are useful and should be further developed and what the users don't like about your new toy.
The author will always be biased in regard of his work. You tend to think that the UI you designed is intuitive, navigation is a breeze and the features are super cool and useful.
When you get the first complaints and usage inquiries on what you thought was pretty straight forward - you realize that your design is not that brilliant and you should get back to work on some adjustments. 

## MVP feature list dilemma

So charged with an eager release motivation, you've bean advised to first release an MVP (Minimum Viable Product). What does that mean? What features should be included to qualify for a Minimum Viable Product?
In the [TestMe Plugin]({{ "/testme/quick-start/" | absolute_url }}) use case, there's a minimal UI that invokes test code generation, that functionality has different outcomes depending on the tested class structure.
What is the minimal set of use cases that should be supported for version 1.0.0? What is considered acceptable and useful and what would be regarded as a malfunctioning piece of junk that completely wastes your time? 
You start maintaining a check list of what features should go into the first release and what should be pushed further down the line in your projects roadmap.
When you bump into some technical difficulties while implementing those features, your struggling hard with the temptation to remove that piece of functionality from the MVP feature list to your projects TODO backlog.
Sometimes that is a sensible choice. Keep being sensible in that manner and pretty soon you find out that instead of solving your problems and delivering value, your left with a mutant that doest not work as you expected and has little value.   

## TestMe motto and current shortcomings
*TestMe IJ Plugin* aims at generating as much Unit Test boilerplate as possible, any code that is based on the tested class signature (white box unit testing) and does not involve logic related to internal implementation - should be generated automatically.
This project is still making it's first steps towards this goal and many use cases are still not covered. To some level, the code generator is opinionated as to how a typical test class is structured and also assumes that a testable class follows some basic principles.
Furthermore, the generated test code adheres to the limitations of the Mocking framework being used (currently, only Mockito is supported). As a result, on some use cases, the generated code might not even pass compilation.
On some cases this is a known limitation taken into account, where the added value of having an auto generated base code as a starting point - overcomes the effort of handling the compilation error.
On other cases, the project simply hasn't gained the maturity level to cover those use cases yet.
If you think you encountered a bug, or a use case where things can be handled better - please report it. Reported issues will typically be prioritized higher than planned features on the projects roadmap.
Same goes to submitted feature requests. I've got no idea what you want if you wont tell me about it :wink:.

Issue tracking is managed at [GitHub Project Issues](https://github.com/wrdv/testme-idea/issues).

[Submit a new issue](https://github.com/wrdv/testme-idea/issues/new){: .btn .btn--info}

Thanks for listening.

P.S. I would like give a special credit for [Michael Rose](https://github.com/mmistakes) and his feature rich Jekyll Theme [ Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) which this site is built upon.
