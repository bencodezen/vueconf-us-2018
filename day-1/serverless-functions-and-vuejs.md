# Serverless Functions and Vue.js by Sarah Drasner ([@sarah_edo](https://www.twitter.com/sarah_edo))

March 27th, 2018 @ 3:00PM CST

## Talk

### Serverless

*   An actually interesting thing with a clickbaity title
*   Goal is to spend less time maintaining and babysitting a server
*   FaaS (Functions as a Service)

### Benefits

*   It's really cheap
*   You pay only for what you use (usually a lot less)
*   Less time babysitting a server
*   Same idea as functional programming, breaking things into small bits
*   You only manage the application

### Functions as a Service

*   The functions are only running when you need them to
*   But this doesn't mean that you should serverless all the things
*   It is good for:
    *   clean data on a cron job
    *   take data nad use it to create data visualization
    *   crop images uploaded by the user and create a user profile

## Vue.js, Stripe and Serverless

*   The application consists of the serverless function which talks to Stripe and separately communicates with a Vuex store

### Google Maps API Powered Data Visualizations

*   Cool demo of the globe with speaker frequency
*   Used a regex to filter down a computed property
*   Uses Three.js to generate the visualization

## Presentation Notes

*   \+ Love the imagery and jokes that come as a result of them
*   \+ Incredible iceberg animation to show what you're actually managing

## Resources

*   [vue-stripe-elements-plus]
*   [E-Commerce Repo]
*   [Serverless Repo]
