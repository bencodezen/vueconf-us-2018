# A React Point of Vue

## About

*   **Speaker:** Divya Sasidharan ([@shortdiv](https://www.twitter.com/shortdiv)
*   **When:** March 28th, 2018 @ 12:00PM CST
*   **Length:** 30 minutes

**Description:** At a glance, React and Vue are like two peas in a pod. They are lightweight component-based libraries for building user interfaces and can be used fairly interchangeably to build scalable web applications. Though they are noticeably different in terms of syntax, their key differences lie in their respective ways of thinking. As a React developer learning Vue, adapting to the “Vue way of doing things” is a challenge that requires a sound understanding of the philosophy behind Vue. In this talk, we will examine the nuances between the two frameworks and cover common mistakes that React developers make when switching from React to Vue.

## Talk

### The Transition from React to Vue

*   Took a methodic approach to learning Vue
*   After about a month, found trouble translating things from React to Vue
*   Took React concepts and brute forced her way and then took a step back to reassess it

### Render Components

*   Think of this in the context as a cup of tea
    *   Even something like this can be broken down
        *   Water
        *   Milk
        *   Tea leaves
*   Uses the sugar analogy as a child that you want to add to the tea
*   Vue is declarative about how something should look, and then we write the logic separately. In React.js, the logic is in the HTML itself

### Render Children

*   Create a cup that has children but Cup itself doesn't have to know about the children
*   In React, you just use the `this.props.children`
*   Vue wants you to separate your logic from your template

### Render Props

*   "The term 'render prop' refere sto a simple technique for sharing code between React components using a prop whose value is a function." - React Docs
*   A way to keep track of 'state' between parent to children

### Render Null

*   Modern web maps render to canvas and it is not declarative
*   It renders in layers in order to display more complex information
*   You can use the `render` function to return `null`

### Final Thoughts

*   Your knowledge prior to coming into Vue is important because it can help work through how you want to use Vue initially

## Memorable Quotes

> ""Componentization is an essential part of front-end development." - Divya S.
> "We're not designing pages, we're designing a system of components" - Stephen Hay
> "Vue affords us the freedom to decide how we want to build things." - Divya S.

## Resources

*   [Repo](https://www.github.com/shortdiv/vueconf2018)
