# Vue In Motion

March 27th, 2018

## Talk

### Intro

*   Animation conveys information visually that could bog down the human brain
*   It allows us to take cognitive shortcuts
*   It keeps them on task and confusion free because they don't have to think about what happened

### CSS Transitions

*   A CSS transition describes how a element should show a change to one of its CSS properties
*   Example: Simple example of ball changing color

### Anatomy of Vue Animations

*   The Vue element for CSS animations is `<transition>`
*   **(!) Planning to show an element frequently? Use `v-show`! because it doesn't remove the node from the DOM**

### Hooks for Animating with CSS

*   When you assign a name to a `transition` element
*   It creates namespaced CSS classes...
    *   enter
    *   enter-to
    *   enter-active
    *   leave
    *   leave-to
    *   active
*   Has a lifecycle for when it enters the page and when it leaves the page
*   You set the transition on the `enter-active` there
*   Start state is on `enter` and finish cycle is `enter-to`
*   Same thing for the leave part as well
*   **(!) She recommends leaving the default state in the original class (which is good for what might happen if animations was NOT supported)**
*   You can add an `appear` attribute to make it appear on mount

### Transition Groups for Coordinating Movements

*   `transition-groups` can wrap multiple elements
*   It gives you another hook called `move` that to watch transforms
*   It's used with the FLIP animation technique
*   **(!) If using multiple items within a transition group, make sure to set a unique key on each one!**

### Managing Toggling Elements

*   `transition` modes are the answer
*   They determine who goes first
*   `in-out` is where the new element animates in first, then when its complete, the current element animates out
*   `out-in` is like when the elemet is like "after you" to the new element

### Animating Static Elements

*   Use manual toggling of classes in order to manage animations
*   Check out Space Oddity CodePen example in Resources

### JavaScript Animation Hooks

*   We are not going to talk with GSAP
*   A "simple" animation with the Web Animation API
*   You can assign functions to `transition` elements which have JavaScript hooks for it
*   **(!) Make sure to `v-bind:css="false"` when animating with JavaScript**
*   You pass the animate function the an array of states, and then an object to configure the timing of the animation
*   You have to tell the JS animation when it is done

### Accessible Animations

*   UI animation can cause negative side effects like
    *   Seizures caused by flashing and blinking
    *   Nausea triggered by parallax motion
    *   Distraction and fatigue brought on by looping animation
*   Apple allowed you to reduce motion in order to minimize
*   There is a 'prefers-reduced-motion' media query
*   Query it and go ahead and change all the animation and transition durations to zero
*   **(!) "Do not use timeout! Use event listeners!"**
*   **(!) Since browser support is only Safari, then you give users the ability to disable the motion.**

## Memorable Quotes

> "Animation is a necessary part of your complete and balanced user experience." - Rachel Nabors
> "Fading text in when you scroll down is a horrible user experience. You're already scrolling down which is 'animating' in the text. Don't do it." - Rachel Nabors
> "There was supposed to be this cool feature, but GPU fire. :laugh:" - Rachel Nabors

## Presentation Notes

*   \+ Like the hand-drawn illustration
*   \+ Nice use of showing the interpolation of the change over time

## Resources

*   [Slides](slideshare.net/CrowChick/vue-in-motion)
*   [Animation At Work](bkaprt.com/aaw)
*   [CSS Animations and Transitions Course]
*   [CodePen Spaceship Opacity Example]
*   [CodePen Space Oddity Example]
*   [CodePen Wipeout]
*   [Web Animations API from Rachel](http://www.rachelnabors.com/waapi)
