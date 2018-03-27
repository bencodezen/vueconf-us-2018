# Keynote by Evan You

March 27th, 2018

## State of Vue

### From 2017

*   GitHub: 37.6k to 84.8k (+122.9%)
*   npm: 1.78m to 9.72
*   Chrome Extension: ...

### Recent Official Releases

*   eslint-plugin-vue 4.0
*   @vue/test-utils 1.0-beta
*   vue-devtools 4.0
*   news.vuejs.org
*   There's a podcast as well!

### Maturing Ecosystem

*   Nuxt 1.0
*   Vuetify 1.0
*   NativeScript Vue 1.0

### vue-loader@next

*   Major rewrite of vue-loader
*   Saw that the architecture ran into a few limitations
*   How it works
    *   High level is that it parses a single file component into the separate parts (i.e., template, script, file)
    *   It is then able to delegate each part to other Webpack loaders so it can handle different pieces of it
    *   Original implementation was a big hack and generating one super long Webpack inline request for each part of the component
    *   This creates a lot of internal implementation consistency
*   Existing Problems
    *   Loading optiosn need to be duplicated between vue-loader and the main webpack config
    *   Loader options must be serializable
*   Instead of inlining all the loaders and the options, you're providing a resource query to each part of the request. With this additional info, you can write Webpack rules to target specific parts of your Vue component
*   The big change is that now you need to include a Webpack plugin.
*   vue-loader 15 clones our existing rules and match them with corresponding pats in Vue components

### @vue/component-compiler-utils

*   What is it? Lower level utilieis for compiling Vue SFCs in more than just webpack (Rollup, Jest, Parcel, etc.)
*   With this utility package, There's already a PR for Parcel even though it was only release a few days ago. So this is promising.

### @vue/cli 3.0

*   In 2.0, it really was a template scaffolding tool. All the webpack configurations are directly included yourself. While you can get access to the webpack directly, there were problems:
    *   Templates are not upgradable
    *   Exposed configuration are intimidating and difficult to understand
    *   Tempalte matinenance difficulty with interweaving features
    *   Forked templates need to constnatly sync with upstream
*   So the goals for the new version
    *   Zero config by default
    *   Additional featurs are shipped as built-in plugins
    *   Everything should be confiurable without ejection
    *   Everthing that isn't build-in should also be implementable as a plugin
*   `vue create -d hello`
    *   `-d` stands for default
    *   It comes with the base configuration
    *   New command for `vue serve` and `vue build`
        *   `vue-serve` spins up a web server with hot reloader
*   For more advanced / production oriented use cases, you'll probably want to select some features
    *   So they ship a way to choose the different configurations you might want when you're configuring your project
    *   `vue create hello`
        *   Choose `Manually select features`
        *   Can choose multiple ones if desired
    *   **(!) You can extract your configuration as a JSON so other members of your team can use!**
    *   The hello world app even automatically links to documentation for the dependencies you include. Very cool
*   Now you will be able to get all the latest changes without breaking your app
*   They are planning to upgrade to webpack 4.0 when the officially release

### Configurations

*   vue.config.js
*   webpack
    *   webpack-merge: This allow you to provide a subset that you want to merge
    *   webpack-chain: The more advanced usage which allows you maximum flexibility to tap in to existing configurations and fine tweak their options
*   Babel / PostCSS/ ESlint/ TypeScript
    *   Use dedicated config files

### What's Next

*   CLI: vue-loader 15 + and ...
*   2.6
    *   ESM browser build
    *   Better async error handling
        *   Handle Promises returned from lifecycle hooks. This will make sure that all errors within promises and async the propagate
        *   $catch method for manually sending async errors to errorHandler. This will allow you to send it to an error handling service
    *   Better warning output (line numbers and codeframes!) for compilation errors
    *   `v-for` iterator support
    *   and other things!
*   2.6-next
    *   Proxy-based reactivity sytsem. This should result in elimination of caveats and allow for more support of data types like Set, Map, etc.
    *   Upgrade codebase using latest ES Features
    *   API remains the same
    *   Both versions maintained in parallel
    *   There will be a small breaking change in the proxy implementation, but most apps should not be updated by this
    *   **(!)This means IE will be out and Edge is the new baseline**
    *   This is a precursor for explorations in the future, because when ES2015 becomes the baseline, it's critical to be able to take advantage of the new features
*   Vuex
    *   Simplify API with async/await
    *   Potentially eliminating the separation of actions and mutations
    *   New scoped-slots based usage pattern that connects the store state getters and dispatch actions into your components so that you don't have to map them individually.
        = This would directly expose the $dispatch function, getters and settesr directly inside your templates
        *   Vuex code would disappear inside the component

### Looking Further Ahead

*   Stability and Evolution
    *   "Where do you see Vue in five years?"
    *   "What happens if you get hit by a bus?"
    *   The team is beyond just Evan now
    *   He believes that the strength of Vue is in the community
*   Introduce an RFC process - `vuejs/rfcs` (to be published soon)
    *   They want to help people understand their thought process when they are creating new features
    *   You have to consider the potential drawbacks, how it impacts current usage, how does it rollout as a feature (i.e., major / minor), long term maintenance, etc.
    *   This will serve as a good way to get involved
*   Release Schedules
    *   Major: 6 months head up, progressive migration
    *   Minor: Every 3 months, 4 weeks beta period
    *   Path: As needed
*   Release Channels
    *   Stable
    *   Beta: Each minor release will go in here for one week
    *   Nightly: If you like to live on the bleeding edge, this would be helpful because we would discover potential regression. There will be a guide for living here
    *   LTS: Receives 18 months of critical patches and security fixes

## Memorable Quotes

> "Now I can say that what was once Vue config issues are now Webpack issues" - Evan You
> "This is a precursor for explorations in the future, because when ES2015 becomes the baseline, it's critical to be able to take advantage of the new features" - Evan You
> "I get that question all the time, but it's not because I'm a reckless pedestrian. :rofl:" - Evan You

## Presentation Notes

*   \+ Like the usage of line graphs to show the growth rate

### Resources

*   [Vue News](https://news.vuejs.org/)
*   [Vue Podcast (in the right rail)](https://news.vuejs.org/)
