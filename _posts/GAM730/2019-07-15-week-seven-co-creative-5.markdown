---
layout: post
title: Week Seven - Co-creative project
published: false
---

**15/07/2019**

The Falmouth face-to-face event - a kind of fringe festival in relation to the Agile on the Beach event - took place at the end of last week. 
Aside from presenting live streams from the Agile event itself, it enabled a group of distance MA students from across a number of disciplines to get together and produce collaborative work in small teams.

# My team's topic - Rural Health & Well-being.

Discussions mainly surrounding social dislocation and lack of resources.
Communities pushed to a minimum, difficulties in working socially, helping each other out due to distance, transport issues, capital compounded by the modern trend of a lack of social meeting places and the tendency to, rather than group together to resolve issues and problems, to remain remote and deal with life on a more individual level.

Community Cat - the cat that wanders around from house to house, 

image from whiteboard
Presentation
What I learned and how it relates to the co-creative project.

AR kit


# Week six webinar: -

**Response to videos**

30s promo
- light tough
- looks nice
- nice and simple

90s instructional video
-Maybe less instructional than informative/ promotional, but that's ok as these are just guidlines
- text a bit fast
- approachable
- inviting
- need opportunity to switch off vibration etc
- good potential for evolution of project, with scoping a potential problem, but also exciting in terms of possibilities - where can it go?

180s funding pitch 
- no graphs, explanation of how money will be made, why would anyone want to invest?
- helps understand the concept better than previous. 
- more instructional than investor pitch
- how much will it cost to developer?
- how long will it take to develop?

Dom: "Accross the three videos there is a distinct lack of detail in the marketing area"

Problem with what geofencing it. I quite like Sam's simple explanation: "Geo-fencing - A virtual perimeter which triggers an action when a user steps within".

"Design is really nice"
We need to export from XD and use them as assets in the app.

**Useful feedback** from peers on Discord and the webinar. 
A little nervousness amonst the team - are the videos up to the level we'd like? Are all our concerns being addressed? There is such little time for Paulo to do what he needs to do and for us to communicate - Paulo is back working nights - and it's clear that, particularly with a short turn-around, it will never be perfection for everbody.

**Still not fully certain how Yosef is getting on** - he does seem to have had problems setting his hardware up, but it's taking a long time even with this consideration. He has had little input into the other aspects of the project.

**17/07/2019**

**CORS** issue - resolved this through discussion with Sam backed up with research and trial and error. It could only be resolved at the server end - Sam found there is a middleware solution that allows Cross-origin Resource Sharing (CORS).
I - we, I assume - have discovered something new through this. Funily enough, a similar issue came up a day or two later at work when building a WebAPI in ASP .NET Core - what a coincidence! And of course I was able to find a solution fairly quickly because I now know what the problem is and where it stems from.

[Cross-Origin Resource Sharing - Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)

[Sam's Laravel solution](https://medium.com/@KrishaWeb/cross-origin-request-blocked-error-in-laravel-5-5-a733232795e4)


**20/07/2019**

The first submission is in! Paulo did a very good job over the last couple of days to get the videos, particularly the investor pitch video, in to shape. We have a final section (how long?) where comparative costs are shown for other app developments by other companies, showing that the amount of funding we want to raise is realistic. [Other notes about the marketing part of the pitch...].
The videos are being hosted on Sam's website set up for the project - mudita.fun.

I began moving my app into pure angular thinking it would be useful if it could be demonstrated in a the browser rather than on Android (probably not iOS as it would need to be published on the Apple App Store, with all the associate difficulties and strict requirements). Some research shows that gyroscopes, compasses and accelerometers are now available through DOM events - [DeviceOrientation Event Specification: W3C Working Draft, 16 April 2019](https://www.w3.org/TR/orientation-event/).
However, I have also now found that it is possible to host an Ionic Framework app as a website - for example of how to do this see [How to Host Your Ionic 4 App as a Website on Firebase & Standard Web Servers](https://www.youtube.com/watch?v=17S9cKSnfwM)- so I have moved the work I have since done in Angular back into Ionic.

It's now working with Sam's API - main missing data at the moment is location, so I have shoe-horned some mock latitude/longitude data into the event-fences being returned from the API. The server website now allows the creation of events and event-fences. Looking forward to being able to add location details.

**Orientation**

Ionic uses a cordova-based plugin for orientation, which is apparently becoming depricated due to the above-mentioned w3.org API. However, it would appear to make sense to use this right now as it will save time. I could always look at other options in the future. [Device Orientation](https://ionicframework.com/docs/native/device-orientation.)

>$ ionic cordova plugin add cordova-plugin-device-orientation
>$ npm install @ionic-native/device-orientation

response: -

>[DEPRECATED] - cordova-plugin-device-orientation
        With the W3C Device Motion and Orientation API now being supported on iOS, Android and Windows devices, this plugin is not needed any more. Read more about the API at https://www.w3.org/TR/2016/CR-orientation-event-20160818/

.. not sure what this really means in practical terms though, as the documentation is not provided for W3C.

This could also be useful, but not right now: [Gyroscope and Accelerometer with ionic 3](https://simpleactivity435203168.wordpress.com/2018/06/28/gyroscope-and-accelerometer-with-ionic-3/): -


This is what I need, I think.. [Agm-Direction](https://www.npmjs.com/package/agm-direction)

>$ npm install --save @agm/core agm-direction

Nope - it's not. This does direction from origin to destination.  It works and could be useful, but not what I'm after. I've left it in for now and commented it out.


So.. I went back and persevered with the Ionic plugin. It took an extreme amount of googling to get to the truth that there were not many options, which led me back to trying to force my first attempt.. It was worth it - it works!!

I needed to put the import declarations in the AppModule and remove them from the explore page's module. I could not explicitly import DeviceOrientationCompassHeading, as the documentation seemed to suggest. Instead I left the variable type as 'any' and assigned magneticHeading to it. Placed it in LocationService and subscribed to it from the explore component. Hey presto!

I now need to find how to create a tone that changes with device orientation..


# note: how to run app in connected device with automatic refresh when updating code

>$ ionic cordova run android -l

The **-l** is the trick to get the auto-refresh.

A reminder how to build the package to install on device: -

>$ ionic cordova build android

[Publishing your app](https://ionicframework.com/docs/v1/guide/publishing.html).

This creates the apk file which can be placed on the device and run locally in order to install.

These blogs are handy for such reminders!

