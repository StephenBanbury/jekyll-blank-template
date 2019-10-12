---
layout: post
title: Week Nine - Co-creative project
published: false
---

**31/07/2019**

Beep is working in left and right in order to indicate direction.

Beep speeds and slows indicating distance.

Relative Bearing indicator shows +/- against zero for direct heading towards closest geofence.

User can opt whether or not to use map.

User can opt whether or not to show visual indicator (currently shown numerically: +/- zero).

User can opt whether or not to use audible sonar beep for direction and distance.

User can opt to indicate the quickest route to closest geofence. This currently only shows driving route (i.e. by road) and causes the map to zoom out uncontrolably to show whole route. If I cannot find a way to fix these issues in the short time available I will shelve this option.


**Next: -**

Investigate using speech (prefarably synthesizer) to say 'left'/'right' and maybe indicate distance.

Implement gauge indicating direction / distance to replace numerical values.

**Desirable**

User-login in order to save and retrieve geofences once found.

Will also improve user safety - issues discussed during webinars and on team thread in Slack.

Potential part-solutions
* email invitation (being implemented by Sam)
* user login/authentication - probably won't be ready in time for submission of prototype.
* we could maybe consider features such as an 'alarm' or 'concern' button - either audible or silently sent to the event organiser.

**UI**

Paulo's designs have lots of potential and provide a unique and recognisable look. I like the Indian theme, which complement the 'Mudita' name and meaning of the word. Sam has concerns about how it may not represent aspirationally for potential clients, but I feel that it is actually our own 'look' and that clients would add their own for their own specific events and aspirations for attracting customers, if this is a requirement for them.

I am not experienced with UI design and know I am likely to struggle to implement anything close to Paulo's designs, but I will attempt to use some aspects of the designs / colours.

**UX**

App flow needs more planning, such as: how does a user commence and approach the event?  Can they select a geofence to find? Where would they start out? Are they given a starting point? 

The way pages flow from one to another is part of this. I have currently used a simple page navigation system with no 'hierarchy' and am using app 'state' to pass parameters between pages. The app could more naturally flow once this has been agreed and finalised and use an efficient method for prior loading only those pages that the use will use. At the moment there are not many pages so it is not such an issue, but is one to consider as development continues and decisions about UX and app flow are made.

**Development process in Ionic Framework**
Whereas web development provides more accessible development tools such as f12 while rendering in the browser - particularly Google Chrome - this is less straight-forward for mobile devices. Ionic is browser-based so I assume (I have no experience to speak of in this field) this makes it a little easier, as it is possible to view aspects of the app in the browser, even if native plugins and, in particular in this case, geolocation, do not work correctly. The best immediate way is to plug a phone or other device into the computer and build the project to render on the device - this is simple, but you do not have access to the browser development tools to check where code is not working correctly etc. I find myself having to work-around this issue by binding variables and information from the code (TypeScript) to elements in the UI itself. This is not ideal but has its uses.

**Yosef** feels he is not being helped as much as he feels he needs - particularly showing him how to use technologies that are new to him. This is a shame, but there is not the time available to teach him new tech and I, personally, have pointed him to online courses that I have used myself. It's also the case that he is working in a specific area that he has much more knowledge in than we do. I think he feels a little on the outside, but he has not been, or made himself, available very much over the weeks of the project, as I have documented previously. He has not added much of any value, if I am brutely honest, which is a shame, not least because he is a very likeable person and could potentially have been an enjoyable addition to the team in terms of working relationships.

**Update**
I've added voice synthesis - using the Ionic Cordova text-to-speech plugin - tells you when you have become closer to a fence other than the one you've been tracking, if it's to the right or to the left, if it is fairly close by, or if it has been triggered. Works really nicely, even if the accent is American!

[Ionic Cordova text-to-speech plugin](https://ionicframework.com/docs/native/text-to-speech)

**Further update**
Added left / right arrow indicators

Speech now signals the name of the geo-fence.

General UX improvements

**01/08/2019**

The speech is a bit annoying - as it relies on geolocation, which can be a bit jumpy and not very accurate at times, so the speech is jumpy. I need to find a way to make it more relaxed and only tell you when there is a definite and prolonged change of direction. Maybe making the bearing calculation less sensitive is one. Another may be to add a delay before it will update you after a previous announcment.

Ajusted accuracy to make it less sensitive - now +/- 20 degrees from straight ahead (ajusted bearing). I could also make this a user-preference setting.

