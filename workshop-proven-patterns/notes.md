# VueConf.US Workshop - Proven Patterns for Building Vue Apps

## About

*   **Speakers:** Chris Fritz ([@chrisvfritz](https://twitter.com/chrisvfritz)) and Eduardo San Martin Morote ([@posva](https://twitter.com/posva))
*   **When:** March 26th, 2018 from 9:00AM to 5:00PM

In this workshop, we'll cover everything you need to know to get started building world-class Vue applications. Topics will include configuring Webpack for single-file components, setting up the most advanced workflows currently possible, how to organize (and reorganize) increasingly complex applications, and more.

## Notes from the Talk

### Background

### What We Will Cover

*   Languages: How JS, HTML and CSS fit in a Vue app
*   Components: Specific tips for building and organizing components
*   Routing: Routes, views, layouts and how they fit together to solve common problems
*   State Management: How to store and access shared state in your application

And maybe...

*   Testing: Making tests as painless and useful as possible with end-to-end tests (with Cypress) and unit tests (with Jest)
*   Enabling best practices: How to avoid arguments and increase productivity by making it easy to do the right thing

### Participation Tips

*   Raise your hands for questions at any time!
*   All examples are public (no need to copy down code examples)
*   Please no recording (to be respectful of the privacy of participants)

### Format

1.  Learn - explanations, examples, stories
2.  Question - clarifications, what-ifs
3.  Apply - code, experiment, one-on-one help

### Single-File Components

*   Explains the basic breakdown of a .vue component
*   When they are compiled, there is still a separation of concerns when it is built
*   Isn't this backwards? No. It is "integration of concerns" rather than a "separation of technologies"

### JavaScript

*   Babel or TypeScript? You can use either. Vue is incrementally adoptable and does not require a bunch of tools in order for you to build in it. Answer: Use what makes you happy and productive on your team
    *   Chooses Babel instead of TypeScript. The explanation is essentially that TypeScript is great, but the advantages don't seem to be there yet. Most bugs are not due to type violations
    *   Explains the difference / what is Babel
*   Babel polyfills vs Polyfill.io - Polyfill.io allows you to only fetch what you need
*   Drop IE support if you can! - You can save up to ~15KB gzipped

### HTML

*   Templates and render functions
*   Templates can be as simple as defining a template property on a component with a string. It can also be more advanced where you use render functions
*   Templates make up approximately 95% of the use case, but one should consider render functions when it is appropriate
*   Templates are fully declarative (i.e., typically only 1 right way to do something)
*   Render functions are more flexible that templates can't do

**(!) Check out anchored-heading rendered component examples that allows you to dynamically generate the heading**

#### Functional Components

*   Stateless and instance-less: No data, computed, etc. and no lifecycle
*   Improves performance: especially for components rendered many times, e.g., with a `v-for`)
*   Can return multiple root nodes. Check out the NavBar for an example of it
*   Don't just use functional components everywhere because it's highly context dependent and you need things like state and lifecycle hooks more than you realize!
*   Sample syntax below
*   You can still pass props and events since it doesn't require the state. It reuses the parent context of its own. It's similar to an $emit
*   Surprisingly, the template can be faster sometimes because it is so highly optimized. An example is how templates cache a static class while the dynamic class can change without updating the original static class

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

**(!) You can define your own inline component within the components definition and actually use the render function to do so. This allows you to create components without creating components**

```js
components: {
    TestInlineRender: {
        functional: true,
        render(h, context) {
            return h('button', 'click me')
        }
    }
}
```

**(!) If you want to return something that's not HTML, you can do this with render functions. Examples are Canvas or WebGL. See "7 Secret Patterns" in resources**

### CSS

*   Global CSS (usually) only in a root `App.vue` component, especially for components rendered many times, e.g., with a `v-for`
*   Scope all component CSS (using either the scoped or module attributes)
    *   Check out Scoped CSS example in the docs
    *   Check out CSS Modules
    *   Recommends CSS Modules instead because it provides "true protection from collisions." It is the same scoping strategy to be used anywhere in the app regardless of where it's used
        *   It takes a little bit of upfront work, but then you're good to go; whereas scoped is the reverse where there's more to learn later
*   The `lang` attribute defines the preprocessor you are going to use
*   Recommends SCSS because you can just use vanilla CSS and it is still good to go

### Components

*   Order of elements - recommends `script` > `template` > `style` because of the relationship between how you "toggle" between the various blocks
*   Always use SFCs. Simpler refactoring even if you are only using a render function to generate your component

#### Useful Patterns in the Style Guide

*   Check out resources for link
*   Use two words for each component to ensure no conflicts occur
*   If you can't use a component more than once, prefix if with `The`
*   Tightly coupling components with naming helps to provide context

#### Wrap Vendor Components With Your Own

*   More easily switch to an alternative
*   Control the interface
*   Allows you to enforce an internal style guide through the components
*   This prevents developers from using the component the wrong way

#### Organization

*   Flat makes refactors easier: no need to update imports after moving a component
*   Flat makes finding files easier: folder scoping leads to lazily named files, because they don't have to be unique

#### Transparent Components

*   Use component element wrappers just like normal elements:

    *   Attributes: You can bind all attributes passed to the component to the direct element.

        ```
        inheritAttrs: false

        <input v-bind="$attrs" />
        ```

    *   Events: You can use custom events to emit the value. You define a `listeners` property within `computed` that can allow you to pass up values up into it if desired. Use spread operator to track other listeners

*   The benefit of this is that you don't have to explicitly define everything and can allow the elments to be as powerful as they were meant to be.

### Routing

*   Keeps all route related files in a router directory
*   Keeps the "pages" in a subdirectory called "views"
*   Also has a "layout" subdirectory for things that you want to share between pages
*   Wrap each "View" with a "Layout"
*   Interesting use of `require('@views/home').default` that is different from the normal `import` syntax

#### View Components

*   Can use in-component route guards: beforeRouteEnter, beforeRouteUpdate, beforeRouteLeave (often better to use route-level guards instead)
    *   Route guards are like lifecycles and can allow you to really fine-tune things, which makes them different components
*   You apparently can use `import('@views/home')` directly on the component of a route
*   Can access $route or accept props from params. Other components also technically have access to $route, but they shouldn't be using it. This seems like a great idea since it abstracts away the concerns that a Vue component has (or does not have for that matter)

#### Simplifying Views

*   By adding a unique key, Vue knows to build the entire page from scratch if the URL changes
*   If you wrap it in `<keep-alive>`, be careful about the number of routes because it can become a memory leak. So you use an `include` property in order to track specific views.
*   There is no more beforeRouteUpdate
*   But this results in slightly slower page render times

#### Meta Info for Views

*   Install the vue-meta plugin which allows you to define a page property on a Vue component / instance
*   This helps to define meta data like page meta info like page titles

#### Layout Tips

*   Even in layouts, avoid global CSS. Keep element selectors in App.vue or nested under a scoped class
*   Nested view components _might not_ have a layout (e.g., for a tabbed interface in a dashboard)

#### Route Definitions

*   You can route gurads to have a route render different components based on the actual state of the application
*   This is great because you can abstract away the logic from being integrated into your app

#### Animate Page Load

*   Before the route resolves, use NProgress to show the animation and give the user an indication that something is happening when they click on a route

#### Lazy-Loaded Routes

*   Apparently you can specify multiple components for a route (i.e., component, loading, error, etc.)
*   You can even define things like delay and timeout

### State Management with Vuex

*   Vuex provides us with a structure for how to manage shared state
    *   The state (i.e., data properties): `store.state`
    *   The getters are like computed properties: `store.getters[]`
    *   Actions are like methods: `store.dispatch`
    *   Mutations are synchronous functions that update the state: `store.commit('COMMIT_NAME')
        *   Actions and mutations look like they do the same thing, so why do we have it?
        *   Because there will be times where you want differentiate how they are used based on certain conditions
*   There is usually one Vuex store in the entire application, but it makes sense to split it up into modules
    *   If you have multiple mutations with the same name, it will actually trigger all of the mutations at once
    *   The solution to having multiple mutations getting kicked off is to set the `namespaced` property to true
    *   The state is not namespaced, but the getters, mutations and actions then get namespaced with the module name prefixed (i.e., a `todos` module will have an action such as `todos/add`)
    *   Sidenote: Prefers to have multiple export statements as opposed to the `export default { ... }` patterns because it allows you to better organize your code and gives you more flexibility
    *   You can set `namespaced` to be default true. Check out the example in `src/state/modules/index.js`
    *   Another trick is to run through all the modules and kickoff the `init` action if it exists since it's a common pattern for actions that need to do things like setting headers

**(!) You can create a `get()` and `set()` with computed properties to help manage Vuex when binding things like input to v-model**

#### Grouped Helpers

*   These are good for grouping together Vuex functions within the components
*   This allows you to then map out repeated actions to various components with a simple include
*   Refactoring becomes a lot easier

**(!) Look into writing generators to help you ease the development workflow. Check out Hygen in Resources**

## Memorable Quotes

> "Integration of concerns" rather than a "separation of technologies" - Chris Fritz
> "The most powerful tool against bugs remain linting, tests, and code reviews- none of which TypeScript solves" - Chris Fritz
> "Unless you have like 10,000+ icons on the page, you're not going to notice the difference between functional and-nonfunctional components" - Chris Fritz
> "Users will wait up to 7x longer if there is a branded animation going on (especially if it's interactive)" - Sarah Drasnger
> "You can even use emojis to name things. In fact, you should always use emojis. It's best practice. 🤣" - Chris Fritz

## Questions

1.  What about naming convention and how Vue handles it?
    *   Recommend PascalCase in order to differentiate between HTML and from a Vue codebase
2.  Is it worth to try and make everything functional?
    *   Only use it when you have to, but you won't see huge optimization improvements unless you have a crazy number of items
3.  How do you know when to break up a component?
    *   It's a gut feeling when you see it. If you feel good about it and the team feels good, you're good. If you feel pain, maybe it's time to refactor.
4.  How do you deal with targeting styles in a scoped parent?
    *   Use `>>>` or `\deep\` to do it
5.  How do you track users scroll point when navigating around an app?
    *   Check out scrollBehavior that allows you to save the position that a user has scrolled to

## Presentation Notes

*   \+ The use of a survey (Typeform) to get a sense of the audience
*   \+ Displaying the results of the audience so everyone gets an idea of who's in it
*   \+ The use of a graph to depict what would otherwise be bullet points
*   \+ Participation tips (i.e., code of conduct) for the audience
*   \+ Actually takes the time to allow for questions in the middle of the talk
*   \+ Leverages the current docs which contain great diagrams and examples and also will help familiarize audience members with it so they can refer to it in the future
*   \+ Allow multiple options for exercises to practice

## Resources

*   [Slides](https://www.slides.com/chrisvfritz/vueconf-workshop-2018-03)
*   [7 Secret Patterns](https://github.com/chrisvfritz/7-secret-patterns)
*   [Polyfill.io (a Babel alternative)](https://polyfill.io/v2/docs/)
*   [Vue.js Style Guide](https://vuejs.org/v2/style-guide/)
*   [Hygen](https://github.com/jondot/hygen)
