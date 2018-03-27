# Deciphering You by Gregg Pollack

March 27th, 2018

## Talk

### What we'll be covering

*   Build a simple reactivity system
*   Learn about template compilation & the Virtual DOM
*   How to create our own render functions

### Make it easier for you to:

*   Code advanced JS
*   Learn how to use the full functionality of Vue
*   Debug your vue apps
*   Extend vue functionality
*   Contribute back to vue

### Start demo / lesson

*   This isn't usually how JavaScript works
    *   Shows example of what happens how total does not change
*   How can we save the total caculation, so we can run it again when price or quantity updates?
    *   So you could save the code, run the code, later on, run stores code again
*   How can we create a more scalable solution, a class to store our dependencies?
    *   Closer to an observer pattern
    *   Vue has a `Dep` class (which stands for dependency)
*   Soon we will have a Dep instance for each variable. How can we encapsulate the code that needs to be watched/recorded?
    *   It's the same code as before, but we want to write a `watcher` function
*   We want each of our variables to have its own Dep instance, so when it's updated it can re-run all the functions that it needs to
*   We need a way to identify which properties are accessed inside each watcher, to figure out which Dep instance to call
    *   We need to know when something is accessed, to call `dep.depend()` on it
*   If we can identify when a property is updated (or set) we can trigger a `dep.notify()` to be called on its Dep class
*   Introducing Object.defineProperty()
    *   Allows us to define getter and setter functions on a property
    *   Make sure to iterate through all of the keys in with an Object of properties to make sure everything is being watched

### Find Reactivity in the Vue Source Code

*   Look in the docs for #data to read about its implementation
*   Where in the source code does data get its reactivity

### Learn about template compilation, the Virtual DOM, and how to create render functions

*   Components template rendering has two steps
    *   Step 1: Compilation: Comile our template into a render function
        *   Can happen on the server of client side
    *   Step 2: Run the render function which creates a virtual node
        *   Only happens on the client side
*   When the code gets sent to the browser, do you want to include the code that is able to compile templates?
*   DOM Trees can get big and have thousands of noes
    *   It's slow, so we use virtual dom
*   A Virtual DOM is a way of representing the actual DOM with JavaScript objects
    *   This is noticeable in the scaling of it since it compares old and new VNodes and makes updates in the most efficient way
*   Think of it as blueprints to the building
    *   If you want to change something in a building...
        *   you can dmemolish everything and start from scratch
        *   Create new blueprints, compare the old and new blueprints and make updates
        *   I want to do the minimal amount of work
*   Steps to intialize component and insert vnode
    *   initalize events and lifecycle
    *   Initialize injections and reactivity (aka state)
    *   if template exists, compile it into a render function
    *   before mount
    *   mounted
*   What happens inside mount?
    *   It generates a watcher on a new target
    *   Once something is rendered, it will trigger a reactive response which then returns VNode that interfaces with the actual DOM and then it is mounted
    *   If reactive data changes,beforeUpdate hook, you compare old and new VNode to patch pieces of the DOM that changed. Then updated is called

## Memorable Quotes

> "You're going to have to accept the fact that you don't know everything that's going on." - Gregg Pollack
> "You probably know this already, but you know, pretty animation." - Gregg Polack
> "The difference between comparing diffs between the actual DOM and virtual DOM is most analogous to blueprints to an existing building." - Chris Fritz

## Presentation Notes

*   \+ Use of story telling into Egyptian pyramids
*   \+ Like the usage of breaking up code snippets into different colors boxes
*   \+ Phenomenal demonstrations of how things are connected and great diagrams
*   \+ Animations are not rushed and really timed well so users can follow where Gregg wants you to focus
*   \+ Love how the diagram is then connected back to the originally "cryptic" diagram
*   \+ Having a breadcrumb trail of the files as you dive deeped in and in is a great way for people to keep track of what is going on

## Resources

*   [VueMastery](https://www.vuemastery.com/)
*   [Vue News](https://news.vuejs.org/)
*   [Vue Podcast (in the right rail)](https://news.vuejs.org/)
