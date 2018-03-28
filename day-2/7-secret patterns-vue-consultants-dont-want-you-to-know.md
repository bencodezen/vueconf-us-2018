# 7 Secret Patterns Vue Consultants Don't Want You to Know by Chris Fritz ([@chrisvfritz](https://www.twitter.com/chrisvfritz))

March 28th, 2018

## Talk

###

*   By making your solutions available, you allow yourself the opportunity

### Productivity Boosts

1.  Smarter Watchers
    *   Watchers accept methods names means you don't have to call the
    *   Make the watch property have a `handler` property for the method you want to call, and you can also flag it with immediate to create it immediately
2.  Component Registration
    *   It's not nice to have to bring boilerplace across every component
    *   You can automatically register components, you can use a webpack feature called `require.context` to specify a regex in a directory to require all the components you want to require
    *   If you're wondering why you there is a `componentConfig.default || componentConfig`, this handles both cases where the `import` does not always take in files that are using `export default`
    *   **(!) Does not recommend doing it with all the components. With non-base components, that means they're always included with your app, which you don't really want**
3.  Module Registration
    *   Use a similar approach to use `require.context` to default import Vuex modules and also add a configuration to namespace them as well

### Radical Tweaks

4.  Lazy-Loaded Routes
    *   In the event you are using a component contains components that are only relevant to them, so you can lazy load the route
    *   In webpack, if you replace a component with a function that returns a dynamic import, then they will download for X component `component: () => import('@views/admin')`
5.  Transparent Wrappers
    *   Vue's customs event works different from a native DOM event. So you need to attach `.native` property to the event
    *   But if you want the event to happen on the child, then you define a computed property that will return and an object of listeners. And now you won't
    *   **(!) By default, attributes not defined as props will be added to the root element of the view**
    *   So you can set `inheritAttrs: false` and then bind the `$attrs` to the child and it then becomes the target for those attributes
    *   Now you don't have to think about what the root component is and it just works great

### Unlocked Possibilities

6.  Single-Root Components
    *   Gives an example of NavBarRoutes within a ul
    *   The solution is using a functional component to return an array that renders in the parent context
    *   Now you can use multi-root components!
7.  Coordinated Transitions
    *   Brilliant example of the curtains example
    *   This is a much cleaner approach and more stable

## Memorable Quotes

> "If you're not trying to make yourself redundant, you're not serving." - Chris Fritz

## Presentation Notes

*   \+ Great use of real code scenarios to deliver the message and drive home the point

## Resources

*   Vue Enterprise Boilerplate
*   [7 Secret Patterns Repo](https://github.com/chrisvfritz/7-secret-patterns)
