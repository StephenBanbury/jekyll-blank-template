---
layout: post
title: Week Two - Building The App Jam Prototype
published: false
---

Building my first prototype
I’ve started by going for option 2 – coordinating a meeting place.
The first thing I found was a javascript haptic feedback library: http://www.hapticsjs.org/
The demo snippets seem to do what I would expect to be able to do, so this may be a way of working with haptics in the browser.
I’m not 100% sure what platform to use, but as I’m most familiar with .NET and Angular, it would seem the latter would be the best option as it’s lighter and more portable and much more easily converted from a web app to a mobile app if needs be, which they probably will!
I’ve decided to set up an angular component for this, which I’ve added to the project that also contains my work game. This is now becoming an application that consists of my prototypes and ideation projects etc.
Next I need to add geolocation to my angular app: checking out https://www.youtube.com/watch?v=lApggVS0icc
Academind has been very useful in the past with Angular so I trust in this.
So.. use https://angular-maps.com/guides/getting-started/ for a package.
We are using a library called AGM.
npm install @agm/core 
Get API key: https://developers.google.com/maps/documentation/javascript/get-api-key?hl=en#key
.. instructions are given here

Key: -
AIzaSyC1FaL6qVPZ9I14REVXtSoGzW4NBI05tSI
Google Cloud Platform: Once a project has been created for the API we can see other available APIs: https://console.cloud.google.com/google/maps-apis/new?project=gam730-app-jam&supportedpurview=project

See keys: -
https://console.cloud.google.com/apis/credentials?folder=&organizationId=&project=gam730-app-jam
I set everything up as expected. However, I get a ‘This page can't load Google Maps correctly. ‘ on the browers and a javascript error in the console: ‘You have exceeded your request quota for..’ which is plainly rubbish as I’ve only just set it up!! When following the exception I find a link to a google cloud platform page shouting out ‘Attention customers in India’!
Eventually it sorted itself out – maybe it is a cache issue / delay?

So.. sorted for getting a lat-long position and showing it on a map.
Next: 
1.	get current position
2.	calculate distance between two positions
3.	find centre point between three positions
4.	

Google maps API key: AIzaSyCSXgPI_1LG_thKRrq92Mu-rfnnUskP9-w

Problem with finding a location that is equidistant between several points on a map. 
It is probably best to firstly find that point and then to look at roads, rail, air etc to find relative journey times. However, even this first task is problematic. Calculations are difficult. I have not been able to find a way to do this.. and I’m not a mathematician. One way may be to use a method similar to artificial intelligence for working out a way of playing a game (ref – GAM710) – i.e. the Black Box approach, where many options are tried and discarded as better options are found – trial and error. This works for computers due to fast processing speed. 
I will need time to formulate such algorithms.
Once this is achieved then I will need to use an API such as Google Roads API and any others I can find to compare travel options.
There is a lot involved, but if it is anywhere close to achievable then it will be worth it and probably reasonably easy to monetize (although research needs to be done for nearest rivals).

My other idea of making a game based on distance and direction between two or more devices may be simpler, if only in a ‘purity’ sense. Whilst there are obviously complications involved, it is a more clear aim with a more obvious path to completion.


Using firebase
Install packages: -
$ npm I –save firebase @angular/fire
add config details (from firebase console) into environment.ts
export const environment = {
  production: false,
  firebaseConfig: {
    apiKey: "AIzaSyDNa6YL1mkT9LI7YxTVUnvb-geXRhrz1FU",
    authDomain: "bomber-defuser.firebaseapp.com",
    databaseURL: "https://bomber-defuser.firebaseio.com",
    projectId: "bomber-defuser",
    storageBucket: "bomber-defuser.appspot.com",
    messagingSenderId: "262462491753",
    appId: "1:262462491753:web:218b7cdf588124b1"
  }
};

Import packages
import { AngularFirestoreModule } from '@angular/fire/firestore'
import { AngularFireModule } from '@angular/fire';



include pixi
ngOnInit is interesting as there’s stuff going on that is asynchronous and it was tricky to get the loading of pixi resources to happen after the loading of players (and their geolocation data) from firebase. 
I’m only using pixi so that I can play with the idea of mapping players onto a canvas – this won’t be too dissimilar to mapping onto a realtime map and then to using sound and haptics instead of graphical representation.

Pixi’s game loop will allow the game to update the player’s location data at regular intervals. When it comes to reading from firebase cloud storage this will happen as the database is updated anyway.


...
then.. 
