# vue-rx by John Lindquist

March 27th, 2018

## Talk

### Introduction

*   Imposter syndrome comes from not knowing why you know something and thus you don't feel validated. Let me assure you that you're all competent developers and good at your job

### Lots of Code Demos

*   imports `Observable` from rxjs
*   This creates a `subscriptions()` property which returns an object and is very similar ot the `data()` property
*   Methods are created in the `domStreams` property and are attached to the elemtn as a `v-stream:event` handler
*   There are some gotchas with streams since they are time based:
    *   If you started smashing the snooze button, you are telling it to repeat the stream again. So you tell is to `share` in order for it to "share" one state
*   If you want to disable the stream...
    *   It is as simple as calling a method to disable it
*   You can merge two events together so that the stream has a "shared state"

## Memorable Quotes

> "The experience seeing how things stream can really help you understand what's going on." - John Lindquist

## Presentation Notes

*   \+ The repeated depiction of live coding for the same concepts over and over definitely helps to reinforce the notion of learning by viewing because it does make the audience more comfortable with the subject matter at hand

## Resources

*   [Slides and Demos from talk](https://www.rxjs.io)
