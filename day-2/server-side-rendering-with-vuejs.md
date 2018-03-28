# Sebastien Chopin (@atinux

March 28th, 2018

## Talk

### What is server side rendering (SSR)?

*   It's been around years
*   You have a request from the browser, the app has a backend that returns the HTML requested
*   Universal apps allows you to use client side hydration once the HTML has been rendered once by the server

### Why Universal?

*   SEO & Social Sharing
    *   Crawlers will see the fully rendered page
*   Faster time to content
    *   Server rendered markup doesn't need to wait until all JS has been downloaded and executed to be displayed
*   Save server resources
    *   The server is working only one time per user to server-render the HTML, then teh user stays on client-side rendering (except if he reloads the page)
*   Great UX
    *   Users have a better user experience
*   Security improvements
    *   Improve the security of your applications by reducing XSS attacks with Content Security Policy (CSP) headers, http only cookies and more

### Demo

*   Use Webpack to create a server and client entry so that there is a server bundle along with a client bundle

### Notes on SSR

*   Each request should have a fresh & isolated app instance
    *   No cross-request state pollution (like a single page app)
*   Pre-fetch data on the server
    *   App state resolved when we start rendering
*   SSR lifecycle hooks: `beforeCreate` & `created`
    *   Avoid starting timers in these hooks to avoid memory leaks
*   Avoid Platform-Specific APIs
    *   window does not exists on the server side, module does not exists on client-side, etc.

### Nuxt.js

*   Vue Server Renderer + Node.js server
*   Interatedmet atag management with `vue-meta`
*   Automatic code splitting
*   Routing based on file structure /pages
*   No webpack config to maintain
*   Extendable with modular architecture

### Nuxt.js Modules

*   progressive wb app
*   axios
*   google analytics
*   vue-apollo
*   awesome-nuxt
*   and more!

### Nuxt 2

*   Not ready for release yet.
*   Try nuxt-edge

## Memorable Quotes

> "It's a lot of work to track what's going on with everything. So we keep track of the webpack stuff so you can focus on building things.

## Presentation Notes

*   Good use of animations to show the flow and difference

## Resources

*   [Nuxt 2 is coming! Oh yeah!](https://medium.com/nuxt/nuxt-2-is-coming-oh-yeah-212c1a9e1a67)
*   Nuxt.js docs
*   [Nuxt Community Board](https://nuxtjs.cmty.io)
