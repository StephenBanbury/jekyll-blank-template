---
layout: post
title: Week Eight - Co-creative project
published: false
---

**21/07/2019**

[Native Audio](https://ionicframework.com/docs/v3/native/native-audio/)

>$ ionic cordova plugin add cordova-plugin-nativeaudio
>$ npm install --save @ionic-native/native-audio

**Useful tip**: I recieved error _ERROR cordova_not_available_ when running in the browser. Research has shown that native plugins can be run in the browser as follows: -

Add 'browser' to platforms: 
>$ ionic cordova platform add browser

to run in browser, including native plugins where possible:
>$ ionic cordova run browser

The plugins don't necessary work correctly - e.g. DeviceOrientation just seems to randomly pole - but at least there's no exception.

**So I now have an ugly beep (which I generated in Audacity) returned with every orientation heading update.**

It doesn't do anything though. I'd like it to move from left to right depending on the heading value. That's next.


Good old stackoverflow - much quicker than expected, I found a way of playing sound that can be panned left to right: [AudioContext panning audio of playing media](https://stackoverflow.com/questions/20287890/audiocontext-panning-audio-of-playing-media) (see the final answer - Septempter 22 2017 - some three years after the original question was asked). 

This solution does not use the native audio plugin as it makes use of HTML5 AudioContext. I adapted the javascript, which uses _document.addEventListener_ 'keydown' to set panning based on arrow key presses, into Angular TypeScript and takes the varying _Heading_ value to centre the stereo image only when withing 5 degrees either side of magnetic north. The audio file I am using at the moment I created in Audacity and is a ticking 'metronome' at 120 BMP. 

Playing around with this I begain contemplating the possibilities of using other sound files, such as music, or voice. The file itself could vary depending on heading, such as telling you to walk when facing your destination. **There is much potential for games or gamification** with this.

**22/07/2019**

I am having all kinds of problems calculating bearing from my location to nearest geofence location. 
Whilst doing this I came across this: [Calculate bearing between GPS coordinates](https://www.perlmonks.org/?node_id=1191753) - what a great idea for an app! This person wanted to create this for his own use, but it's a fantastic use of geolocation - i.e. finding your way back to a saved place when on a hike (this is in Canada - I doubt you'd need this extravagance when hiking in most of the UK).  Pity it's written in Perl - I now need to learn a bit of Perl if I'm to use this function!

Amongst the many useful references to this subject I found, most of which are mathematical formulae that are beyond my needs or comprehension, I found this, again on **stackoverflow**: [Calculate compass bearing / heading to location in Android](https://stackoverflow.com/questions/4308262/calculate-compass-bearing-heading-to-location-in-android). I realised that there is a simple calculation to be made to find the bearing to a specific location, as north on the map is always the x axis: headingToFence = heading - bearing, where heading is direction facing in relation to true north and bearing is the angle created between current lat/long and the geofence lat/long in relation to grid north. 


'  bearing(a1: number, a2: number, b1: number, b2: number) {
    const TWOPI = 6.2831853071795865;
    // if (a1 = b1 and a2 = b2) throw an error 
    let theta = Math.atan2(b1-a1, a2-b2);
    if (theta < 0.0)
      theta += TWOPI;
    return this.rad2deg(theta);
  }
'
  
**24/07/2019**

**Sonar Compass - Distance and Direction**

Spent much of the past couple of days getting the compass orientation working correctly and tying it in with the audible sonar as a  direction and distance indicator. I had thought the orientation was working, but found this to be a red herring because it only 'appeared' to work under certain circumstances. As soon as I began walking around I found my relative location drifting and my compass heading began to take on a life of its own, my actual heading bearing no relation to the actual bearing towards the nearest geo-fence. I did get the sonar working correctly in terms of speed of pulse representing distance, but the left-right panning to indicator direction was awry. Again, perserverance won the day - more research and deep thought eventually let me to the solution, where I needed to calculate the bearing from the device's coordinates towards the geo-fence's coordinates, and then calculate the relative bearing - or offset - in order to fine-tune the bearing using the sonar panning, enabling the user to home in on the actual bearing. I'm using a 10 degree offset either way, which appears to be a comfortable margin for now. 

[stackoverflow help](https://stackoverflow.com/questions/46590154/calculate-bearing-between-2-points-with-javascript) led to this function: -
`
  bearing(startLat, startLng, destLat, destLng){
    startLat = this.toRadians(startLat);
    startLng = this.toRadians(startLng);
    destLat = this.toRadians(destLat);
    destLng = this.toRadians(destLng);
  
    const y = Math.sin(destLng - startLng) * Math.cos(destLat);
    const x = Math.cos(startLat) * Math.sin(destLat) -
          Math.sin(startLat) * Math.cos(destLat) * Math.cos(destLng - startLng);
    let brng = Math.atan2(y, x);
    brng = this.toDegrees(brng);
    return (brng + 360) % 360;
  }
  
  private toRadians(degrees) {
    return degrees * Math.PI / 180;
  }
  
  private toDegrees(radians) {
    return radians * 180 / Math.PI;
  }  

  and the confirmation of the concept of 'relative bearing' from [diydrones.com](https://diydrones.com/profiles/blogs/the-difference-between-heading)

`
  relativeBearing(bearing: number, heading: number) {
    let relativeBearing = heading - bearing;

    if(relativeBearing < 0) {
      relativeBearing = relativeBearing + 360;
    }
    return relativeBearing;
  }
`
When relativeBearing = 0 the device's heading is directly towards the geo-fence.


In order to achieve the speeding/slowing of the sonar relative to distance, I changed the background 'ambient' metronome for a single beep, which is played from within a javascript SetTimeout function which is called recursively in order to allow for a delay that is variable depending on the distance from the geo-fence.   

I don't want to rely purely on sound - the idea is to be as flexible as possible and allow for as much freedom as we can - so I also use some visual clues. The closest geo-fence is highlighted in pink (arbitrarily) and the user's location mark changes to blue when very close. I will be adding further indicators, both visual and audible, as I go. Also hope to introduce **haptic feedback** at some point.

**The team**
**Sam** is continuing to work on the server-side and has now introduced location (latitude and longitude) to the geo-fences. Fences are also editable from the server/admin front-end app.  My client app now uses these coordinates rather than the fake ones used up to this point. Sam is working in Edinburgh for the next five weeks, but as we are used to working remotely this should hopefully present little in the way of problems - it has certainly not thus far.
**Paulo** has been doing further work on the general design - look & feel mainly - for the app. He has started using Indian style mandalas, which do add a nice touch. We have begun discussing how the designs will find their way into the server and client-side apps - much discussion and thought will be required for this.
**Yosef** is still problematic, in the sense that he only drops in once or twice a week, making a brief entry into the Slack channel, one which does not really have much relevance or offer anything to the project, and then disappears again for days on end. I believe he is still struggling to post something from his arduino setup to Sam's server, but he has not hung around long enough to engage and discuss the issue in order to find a solution. His is not a subject the rest of us have experience with, but although we are happy to help if and where possible, he has not been open, or available, to discuss any such issues. It's a concern to an extent, but so far it has not been detrimental to the continuing development of the project and, although his input on the potential physical web aspects we have discussed would be welcome, I suppose his lack of presence actually means that there is less potential worry in terms of potential problems of working with a larger and more skill-diverse team. I feel for Yosef, but he has not expressed anything in the way of concerns or explanations for his lack of involvement - apart from work, which is something we all have to deal with - so it is difficult to engage him further or to resolve any issues he may be having. Still, it is huge shame that we are not utilizing the potential for physical web and physical aspects to the concept and project development. We did discuss, as a starting point, a physical button to start a timer or to acknowledge the physical presence or a user. Surely more could come from this, but as an initial way of incorporating the physical web this seems to have potential. Further development of such ideas could begin to incorporate 'beacons' which could act in a similar way the 'virtual' web we are currently working with, where devices could be recognised when in the presence of a beacon and content could be streamed. It would be very nice to take this idea and to develop it once the potential had started to become more apparent through experimentation.
Yosef has expressed a desire to learn Angular and general web development, having mentioned these this week and enrolled on a Udemy web 'boot-camp' course, but this is not the time necessarily to be doing this as the role we discussed and agreed with him had no such involvement, and it's come a little from left-field.

[Mapbox turorials](https://www.youtube.com/playlist?list=PL86WBCjNmqh6gMUI3cKW-vZQBWt_-hsqp) look interesting - 3D geolocation development in Unity. I'd like to take a look at this.

[Mapbox](https://www.mapbox.com/?utm_medium=sem&utm_source=google&utm_campaign=sem|google|brand|chko-googlesearch-pr01-mapboxbrand-br.broad-intl-landingpage-search&utm_term=brand&utm_content=chko-googlesearch-pr01-mapboxbrand-br.broad-intl-landingpage-search&gclid=CjwKCAjwg-DpBRBbEiwAEV1_-JPk1ndiPSfL9M9XMslXQBLzJwpbqVj2ky45CKpOt1sNCJjyzKEFMxoCiB4QAvD_BwE)

**Course material**

I am finding myself falling behind with the weekly course material, so I will now spend some time catching up.




