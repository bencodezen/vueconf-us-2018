# VueConf.US Workshop - Proven Patterns for Building Vue Apps

*   By Chris Fritz and Eduardo
*   On October 9th, 2017 @ 9:00AM

## Background

## What We Will Cover

*   Languages: How JS, HTML and CSS fit in a Vue app
*   Components: Specific tips for building and organizing components
*   Routing: Routes, views, layouts and how they fit together to solve common problems
*   State Management: How to store and access shared state in your application

And maybe...

*   Testing: Making tests as painless and useful as possible with end-to-end tests (with Cypress) and unit tests (with Jest)
*   Enabling best practices: How to avoid arguments and increase productivity by making it easy to do the right thing

## Participation Tips

*   Raise your hands for questions at any time!
*   All examples are public (no need to copy down code examples)
*   Please no recording (to be respectful of the privacy of participants)

## Format

1.  Learn - explanations, examples, stories
2.  Question - clarifications, what-ifs
3.  Apply - code, experiment, one-on-one help

## Single-File Components

*   Explains the basic breakdown of a .vue component
*   When they are compiled, there is still a separation of concerns when it is built
*   Isn't this backwards? No. It is "integration of concerns" rather than a "separation of technologies"

## JavaScript

*   Babel or TypeScript? You can use either. Vue is incrementally adoptable and does not require a bunch of tools in order for you to build in it. Answer: Use what makes you happy and productive on your team
    *   Chooses Babel instead of TypeScript. The explanation is essentially that TypeScript is great, but the advantages don't seem to be there yet. Most bugs are not due to type violations
    *   Explains the difference / what is Babel
*   Babel polyfills vs Polyfill.io - Polyfill.io allows you to only fetch what you need
*   Drop IE support if you can! - You can save up to ~15KB gzipped

## HTML

*   Templates and render functions
*   Templates can be as simple as defining a template property on a component with a string. It can also be more advanced where you use render functions
*   Templates make up approximately 95% of the use case, but one should consider render functions when it is appropriate
*   Templates are fully declarative (i.e., typically only 1 right way to do something)
*   Render functions are more flexible that templates can't do

**(!) Check out anchored-heading rendered component examples that allows you to dynamically generate the heading**

### Functional Components

*   Stateless and instance-less: No data, computed, etc. and no lifecycle
*   Improves performance: especially for components rendered many times, e.g., with a `v-for`)
*   Can return multiple root nodes. Check out the NavBar for an example of it
*   Don't just use functional components everywhere because it's highly context dependent and you need things like state and lifecycle hooks more than you realize!
*   Sample syntax below

```
<template functional>
    ...
</template>
```

OR

```
export default {
    functional: true,
    render(h, content) {
        ...
    }
}
```

## Memorable Quotes

> "Integration of concerns" rather than a "separation of technologies" - Chris
> "The most powerful tool against bugs remain linting, tests, and code reviews- none of which TypeScript solves" - Chris

## Presentation Notes

*   \+ The use of a survey (Typeform) to get a sense of the audience
*   \+ Displaying the results of the audience so everyone gets an idea of who's in it
*   \+ The use of a graph to depict what would otherwise be bullet points
*   \+ Participation tips (i.e., code of conduct) for the audience

## Resources

*   [Slides](https://www.slides.com/chrisvfritz/vueconf-workshop-2018-03)
*   [Polyfill.io (a Babel alternative)](https://polyfill.io/v2/docs/)
