### How We Do Vue At GitLab by Jacob Schatz

March 27th, 2018 @ 10:40 AM CST

## Talk

### What We Needed

*   Easy to contribute
*   Fast to learn
    *   You didn't need to know
*   Concepts work on their own
*   Not gargantuan
*   Why Not Choose...
    *   React
    *   Mithril
*   There are no "wrong answers," but Vue was the best choice for them because it has the smallest learning curve and had the most
    Vue was drop-in: We didn't have NPM, webpack, so we could start right away without those tools

### Main Concept

*   Vue has a small initial learning curve
*   If you understand these 8 lines of code, you understand Vue
*   People can already be productive with this small amount of code
*   People can be productive immediately
*   What's the smallest common demonitator to get someone up and running?

### Why Vue?

*   Both opinionated & not opinionated
    *   It has this whole ecosystem and offers solutions to solve those problems
    *   On the other hand, you don't have to use any of those things and it still works well
*   Release on the 22nd NO MATTER WHAT
    *   In review by 1st and merged by the 7th
    *   There is no time to waste
    *   No time to refactor everything
*   Let's add in Vue, but first...
    *   Our baggage:
        *   jQuery & CoffeeScript
        *   Remove CoffeeScript
            *   CoffeeScript was designed as a solution to problems that ES5 had
            *   But ES6 came along and solved all of these problems
            *   So there was no need for a non-standard language
            *   It was hard to find people who wrote CoffeeScript
            *   Most devs was already good at JS
            *   Took the source that it compiled and then got the ES5 out of it, and then rewrote it to ES6
            *   The benefit of this is that all the tests still pass, because it ultimately is the same source code
            *   Once they did this, people contributed more
            *   Then they added webpack
            *   Then they could take the ES5 code and turn it into ES6
                *   Did it on an as needed solution
                *   It works and they need to write new features, so they were only updating it when they were actually interacting with it
*   Rewrite everything? Absolutely not!
    *   Because you need progressive enhancement
    *   You need to develop new features while using new syntax
    *   Start simple get complex later
    *   Good solution but has problems:
        *   Syntax highlighting in GL doesn't exist
        *   Performance
        *   So add in VueLoader
        *   Which netted them a huge performance boost
*   Outcomes
    *   Life is easier
        *   Because less bugs
        *   Because there was less code
        *   Becuase less event management
            *   Rails comes with TurboLink, which is great, but if you don't write it correctly, your JS events would get removed. Yikes! Vue made this easier by taking care of events
        *   Had a lot more reusable code
            *   This menas you're writing less code
        *   Organizing code
            *   Everyone was writing it just a litle bit differently
            *   How do you figure out what the "right" way is?
            *   Adopted Vuex
                *   Solved a lot of their problems
                *   They can rely on the docs and suggestions
                *   It was the right time for the opinionated stuff to come in
                *   With the virtual DOM and everything, that page became faster than all the competition because things were rendering a lot faster
                *   Everything that Vue is taking care of, you aren't thinking of it when you're writing jQuery
        *   Created their own docs
            *   docs.gitlab.com/ce/development/fe_guide/vue.html

### The Present

*   Removed CoffeScript
*   Switched to ES5
*   Switched to ES5
*   Added in webpack
*   Write big features in vue
*   Use vue loader for easy programming and performance
*   ???

### Reusable Components

*   The problem is that GitLab is not 100% Vue.js
*   CSS is not reusable because of the way it was originally written
*   Styles are not 100% consistent
*   Solved it with PostCSS and vue-loader
*   Needed two approahces
    *   Where components exists only in Vue
    *   Where components exists in and out of Vue
*   Their solution was to use Bootstrap 3 as base overrides styles
*   It's an organized way to fit Bootstrap into GitLab
    *   Follow all of the Bootstrap conventions
*   What about Bootstrap 4?
    *   Go with boring solutions
*   Vue Component vs CSS Component
    *   Organizes CSS components with each inside its own directory
    *   Separates out the skin, layout and variables
    *   **(!) Like the naming convention of `$grey-200`**
*   When components exists only within Vue, then they use the style tags, otherwise the styles lives in two places. Big performance boost!

### Looking Back on the Journey

*   Started with jQuery, CoffeeScript and inline scripts
*   Ended with Vue, webpack, Vue Loader and Vuex
*   Not the real story,
*   Started with a lengthy annoying develpment experience
*   when we saw this, we decided that we could make it better. We ended with a quicker more leasant development experience

## Memorable Quotes

> "All of these frameworks 'work', but the reality is will it survive when you build something large that will scale." - Jacob Schwartz
> "It's not about the using the latest and greatest framework, but creating the best developer experience possible." - Jacob Schwartz

## Presentation Notes

*   \+ Like how he shows real examples from their codebase to illustrate his point

## Resources

*   [GitLab Team's Vue Usage Documentation](http://docs.gitlab.com/ce/development/fe_guide/vue.html)
