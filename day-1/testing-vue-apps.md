# Testing Vue Apps by Edd Yerburgh

March 27th, 2018 @ 12:00PM CST

## Talk

### Why Test?

*   Check application works correctly
*   Provide documentation
*   Easier debugging
*   Less bugs (by anywhere from 20 to 80%)

### Downsides

*   Avoid writing too many tests that tie us into an implementation that make it difficult to refactor

### Front-End Testing Pyramid

1.  e2e Tests
    *   Code that "opens a browser, runs the application and ensure everything runs correct"
    *   This is nice, but they are difficult to debug and are slow
2.  Snapshot Tests \*
    *   Take a snapshot of a component and takes a new snapshot when it's rerun to compare it against the original test
    *   They safeguard against unintended changes
    *   Snapshots tests are quick to update
3.  Unit Tests
    *   Tests the scenarios of a function
    *   They are easy to debug and really fast
    *   For Vue FC, uses the wrapper to mount the component and test it
    *   **(!) Do not check for the existence of a class to verify things, it's bad practice**

### Component Contract

*   It is the API or the interface that your component has
*   It is the details that the users would need to know in order to use your component
*   The details that I put in the documentation are part of its contract

## Presentation Notes

*   \+ Nice use of workflow to show what's going on.
*   \+ Demo of Jest is very effective at getting buy in from those who have yet to buy into it

## Resources

*   Vue.js Testing in Action MEAP - Book coupon `ctwvueconfus18`
