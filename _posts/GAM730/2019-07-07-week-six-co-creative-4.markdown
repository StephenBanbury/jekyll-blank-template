---
layout: post
title: Week Six - Co-creative project
published: false
---

**07/07/2019**

Sam & expressed concerns that the project is not fully bought into by the group as a whole. Worth considering the reasons this may be, what could have been done differently, lessons learned, what is to be done?
(see Slack on this day)

Decided we needed to slow down the dev of the XD video presentations etc and all get on board. Need to script it, and allow the development, story, narrative etc of the project itself to follow the design. At the moment all the parts are still somewhat separate entities. Thinking of user experience first, the app needs to meet users requirements as a basic point. (speak to Pascal).

We are writing up the videos and will discuss and amend as necessary and move on from here.

Yoseph has his Arduino kit and is building something that will be able to talk to Sam's server.

**Tech notes**

I've managed to move my angular app into the ionic framework. I have started making use of ionic ability to create a UI that utilises a device's own native features. I am currently playing with navigation - uses angular's routing - started with tabs and pages, but I'm not sure I should not be just using components - passing parameters, or maintaining their state, more specifically, may be more problematic than it's worth. I'm possibly misusing the way Tabs are supposed to work. 

Currently the flow is 
* home page - select from a list of events
* explore page - use geolocation to move around and find geofences. Once found, the details of the geofence can be viewed.
* fence page - display the information and content relating to the found geofence 

**explore**

Made it possible to show or hide individual map markers. For the moment I've set it to hide them all but show it once within 5 metres. There are messages to tell you when you are close then when it has been found. What I need more than anything now is to show

1. how far (visual, haptic) away the geofence is and 
2. what its direction is.

**fence**

will need to get details from Sam's API. Currently I'm getting a link to a random picture from [Unsplash API](https://api.unsplash.com)


**next**

I'm looking for how to package an ionic app so it can be installed on an Android device for testing.
This could be useful [Deploying to a Device](https://api.unsplash.com).
Nope! Like most of the official docs it only mentions doing this via the Play Store or Apple Store. I need to test on my device as geolocation is no good if you cannot move around without taking your whole dev set-up with you.

Good ol' Stackoverflow looks more promising: [Run Ionic Android App natively on device with out being plugged in](https://stackoverflow.com/questions/50520619/run-ionic-android-app-natively-on-device-with-out-being-plugged-in)

>You can build the apk and install it on your Android device.

>1) Go to Build>Build apk(s) 2) After it is done a popup will be shown by the Android Studio. Click on locate and you will find your .apk file as 'android-debug.apk'.

>You can then make a link by uploading it on diawi.com or any other app sharing tool, and install it on your phone using that link. That way it won't need to be plugged in to your system.

hmm.. do I really need to do this with Android Studio?

.. then on the Ionic forum[Build done but could not see apk .why?](https://forum.ionicframework.com/t/build-done-but-could-not-see-apk-why/120603/4)

ionic cordova build android
ionic cordova build android --prod

.apk file is then here: C:\Dev\Repositories\mudita-client\mudita-client-ionic\platforms\android\app\build\outputs\apk\debug

Copied this file to a newly-created Dev folder on my device and ran it to install it.

It works! My first Android app (in development of course).

The geolocation does not appear to detect me though - map not showing my location. I've had this issue when debugging in browser so it  may the same issue. 

Is this actually trying to track me though? I think I need to have a way to show i'm being tracked rather than waiting for the map to update to my location. 

Nothing coming back from geolocation

Discovered it works if I use ionic geolocation, which is based on W3C geolocation api specification.

>This API is based on the W3C Geolocation API Specification, and only executes on devices that don't already provide an implementation.

Not quite sure what happens on devices that do already provide an implementaion..

>$ ionic cordova plugin add cordova-plugin-geolocation
>$ npm install @ionic-native/geolocation


Next is [Device Orientation](https://ionicframework.com/docs/native/device-orientation).


**08/07/2019*

But first..

It's API time. Sam has given me the url for a list of events.
It's works fine in the browser but not from my app. Seems to be a CORS issue - exception is 
>Access to XMLHttpRequest at 'https://mudita.fun/api/v1/events' from origin 'http://localhost:8100' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.

[stackoverflow](https://stackoverflow.com/questions/20035101/why-does-my-javascript-code-get-a-no-access-control-allow-origin-header-is-pr)

[Using CORS](https://www.html5rocks.com/en/tutorials/cors/)

this looks like a pain!

For dev work in Chrome - I'll have to test if this works in the app later..

[Chrome plugin for Allow-Control-Allow-Origin](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi?hl=en-US).

With that sorted I don't seem to be able to get data from Sam's API - no exception, just no data.

**pain**

I've been trying to mock Sam's data output but it's a pain trying to make it fit, as I've build this using the format suggested a couple of weeks back. Too many api calls are required to get everything required. 

Should I use persisting data in the service?

Should I change navigation so we are not using ionic's pages paradigm?
Should I continue with this when it may be simpler to ask for the data in a different format? this would be simplest in the short term, but I may be putting off an innevitable necessary change..

