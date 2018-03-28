# Agile Designs Systems (with Vue) by Miriam Suzanna ([@MiriSuzanne](@mirisuzanne))

March 28th, 2018

## Talk

### Intro

*   Design systems can include colors, sizing, space, etc.
*   This has been around for a long time
*   Design Systems: Style Guides + Tookkits + Pattern Libraries + ???
*   Remember that you have to start somewhere
*   You need to know what components we got
*   It is an **integration** of design and code. It doesn't make sense for one person to be doing it
*   Not just what it looks like, but how to build it as well
*   Since they are consultants, they need to make the design system as a byproduct if possible
*   Code Patterns: How do we add meaning to the code

### Where Do We Start?

1.  Start with a design audit. Skip if starting from scratch
    *   Take screenshots of the app and figure out how to group them
2.  What do we need?
    *   What components wil it require?
3.  Start with design tokens
    *   Colors exist outside of their use
    *   Start somewhere, stay agile
    *   Keep the top levels output free
    *   Classes are for pattern marking and can be seen as an API
    *   Problems with Sass Variables / CSS Variables
        *   Not meaningfully organized
        *   Encourages one-offs
        *   Difficult to automate
    *   Decided to use Sass Maps, but that had issues with references
    *   So they came up with their own syntax and tooling (i.e., Sass Function)
    *   Global Settings >> Theme Defaults >> Component Details

### The Lazy Option

*   Document everything directly from the code
*   They are using Herman which is like SassDocs

### Other Concepts

*   You should always keep in mind what your users will have and build a design system API that fits that stack
*   You can move name-space things into data-attributes
*   Automation is essential because it keeps it up to date. Because up to date documentation is more important than comprehensive documentation.

## Memorable Quotes

> "I put in an animated SVG here to keep up with the other designers." - Miriam Suzanna
> "You are not MailForce or InstaFace (unless you are)." - Miriam Suzanna
> "If it's not documented, it doesn't exist." - Miriam Suzanna

## Presentation Notes

*   \+ Effective use of random scribbles to give an authentic feel to the talk
*   \+ Great use of the old metro standards
*   \+ Like the Lego analogy
*   \+ Funny use of emojis to represent a diverse cast
*   \+ Like how photos from day 1 conference were incorporated as slides

## Resources

*   [Slides](https://oddbooksapp.com/book/agile-design-vue)
*   CssStats
*   Herman
*   SassDoc
*   VueD (with Theo)
