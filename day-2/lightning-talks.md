# Lightning Talks

March 28th, 2018

## Talks

### Complex Application State by Patrick Seda ([@pxtrick](https://twitter.com/pxtrick))

*   Uses the analogy of the ceiling fan
    *   Four states: (1) off, (2) slow, (3) medium, (4) fast
    *   When you pull it, the next state is dependent on the state
*   Treat the Finite State Machine (FSM) as an external service that does things for us
*   The FSM would communicate with the Actions in Vuex

### Reusability: Is It Worth It? (SheltonClinard [@SheltonClinard](https://www.twitter.com/SheltonClinard))

*   So you get a side bar that constantly gets tweaking requirements
*   Questions to ask is:
    *   Even if there are similarities, do they have shared functionality?
    *   Are any children shared?
*   Where I draw the line with reusability is whether any functionality is actually being reused

### Beyond HTML with Vue by Eduardo San Martin Morote ([@posva](https://www.twitter.com/posva))

*   Data Providers
    *   State animations with springs
    *   Lazy Sudoku Example
    *   Declarative Promises (Vue-Promised.js)
*   Sound & Music
    *   You can bind props like the rate of sound
*   3-D
    *   Canvas render like Three.js
*   Cool Dancing Cube Example
*   [Slides](https://slides.com/posva/beyond-html-with-vue)

### The Dream: A Full Rewrite by Seth White ([@fluffydev](https://www.twitter.com/fluffydev))

*   Why not a full rewrite?
    *   Like remodeling a kitchen while building a new house
    *   Difficult to convince others (cost/benefit)
    *   Difficult to QA
    *   How do we get that sweet Vue goodness?
        *   The answer is one stab at a time
        *   Any time you have an enhancement or bugfix, you change it
*   Drawbacks
    *   Library size
    *   Complexity
    *   Possibly longer dev time
    *   May not be considered "best practice" (at first)

### 40 Hour Plan for UX Proficiency by Jacob Covey

*   UX Proficiency: The ability to create high quality design solutions with UI mockups and prototypes
*   Do you even UX? Should you?
    *   Yes
*   So what's the plan?
    *   [DevsLearnUX.com](http://devslearnux.com/)

### OverVue of Vuetify.js by CJ

*   What is Vuetify?
    *   It is an implementation of the material design guidelines
    *   Created by John Leider
*   Why Vuetify?
    *   Has a lot of components
    *   Semantic naming
    *   Fantastic documentation
    *   Extremely easy to get started
*   The docs are very comprehensive

### Reactivity: Learning by Accident by Jeff

*   Gotcha #1: Adding and removing properties
*   Gotcha #2: Modifying array indices
*   Gotcha #3: Relying On immediate DOM rendering

### Build a MiniFlix Clone with Vue Contest by Dan Zeitman

*   bit.ly/vue-video
*   They use GitBook for documentation
*   Content to use Cloudinary to build an app

### Code Splitting Patterns with Vue by Sean Larkin

*   Code splitting
    *   Google Web Toolkit - Pionneer of this technology
    *   Process of splitting your code int oasync chunks (at build time)
    *   The power of code splitting is that webpack will create a separate bundle for only that piece of functionality
*   Why...
    *   The future of the web is mobile
    *   Average mobile website take 14 seconds to get interactive
    *   50% of your users will leave your site if it takes more than 3 seconds to load
*   Top 3 reasons it loads
    *   Number of JS is initial download
    *   Amount of CSS
    *   Amount of concurrent network
*   Goals:
    *   <=200kb uncompressed intiial JavaScript
    *   <=100kb uncompressed initial CSS
    *   HHTTP: 6 initial network calls
    *   HTTPS/2: 20 initial network calls
    *   90% of code shipped should actually be used
*   Two types: static and "dynamic"
    *   Use static when your using "heavy" JavaScript
    *   Anything temporal
    *   Routes
    *   "Nothing in webpack can be purely dynamic" because it's an anti-pattern for static analysis
*   How does it work with Vue?
    *   The first framework to craft a developer experience with webpack in mind
    *   Code splitting is a first class citizen
    *   If you want to take any component to async, all you have to do is turn the component as an functional import
*   You can apply this:
    *   Routes: Always
    *   Component: Temporal
    *   Lifecycle: Conditional
*   Antipatterns
    *   Automatic code splitting / code split everything
    *   Libraries that code split in their own code
*   Look out for mini-css-extract which will lazy load CSS
*   Check out the Chrome Coverage Feature

## Presentation Notes

*   Like the usage of wireframes to simplify understanding of complex components like Vuex
*   Good usage of workflows to let users keep track of how things are progressing
*   Nice simple block representations of components
*   The se of bold colors with nice large titles
*   Great demo of the dancing cube code
*   Fun use of a game to represent trying to kill legacy code
