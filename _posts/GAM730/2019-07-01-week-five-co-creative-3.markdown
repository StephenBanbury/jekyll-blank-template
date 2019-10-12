---
layout: post
title: Week Five - Co-creative project - team and project building
published: false
---

**01/07/2019**

We had been reaching a point where there was concern that Y has not been able to engage with the project.
He had produced some very basic HTML that was only just still current ten years ago and was basically a few simple <p> and <h1> tags and some text, with a <img> placeholder for an image.
It was a difficult situation and some tensions started to be exposed.
We had our previously-arranged weekly skype meeting and discussed finding ways for him to really get involved in something he has interest in. Being the easy-going guy he is, he had allowed himself to go along with whatever he felt was the direction the project is taking. Whilst liking the ideas we have put forward and started working with, he had not contributed any new ideas or had much in the way of influence. 
However, we helped devise a mechanism for his involvment - one that will not just hold his interest but will hopefuly allow him to become fully invovled in the development of ideas as his imagination is provided the scope and freedom to express itself; it also has the potential to add to the overall concept and maybe move it in new and interesting directions. 
It was suggested he start playing with arduino, or any other hardware solutions he thinks suitable, and to experiment with transmitting via WiFi (or other) over HTTP to send signals to the server we are putting in place. This can be then used in various possible ways - start/stop button, help button etc.. we will develop the potential once we have a successful input.
It is interesting that, once we had made this step, I sensed a vastly increased sense of commoradary and team-ship, and we began talking in a much more free and uninhibited manner. The importance of everyone feeling part of the team, a common sense of direction and comfort in what we are trying to attain and an equal part to play etc. became sharply defined.

We talked about the potential for companies to use Mudita for creating events that advertise or create awarenes of their brand and products. We also discussed the potential for cultural or heritage events, such as St Fagens Museum of Welsh Life. I will try to set up a meeting with Pascal.

**Paulo** has come up with some nice video work that we can build on for the pitch. He's used Adobe XD and it looks professional. He's obviously been thinking hard about the pitch and the way the medium he is working within can be used to get our message across. It also helps define the message itself!

**Technical notes**

I have managed to take my angular app and convert it into an Ionic Framework app. I am hoping this will allow more native plugins to come into play for the likes of haptic feedback, gps and the in-built direction/compass hardware most devices have.

This is new to me, and I am investing time reading the ionic documentation and following suitable tutorials for the technical details of how to achieve these kind of aims.

1. Installed ionic framework
2. created new ionic project (ionic start mudita-client) with tabs
3. spent some time copying the code for modules, components, services, models etc over to new project. This was not very easy and required some trial and error. But I got there in the end. There is not an exact correlation between an Angular and an Ionic app, particularly where navigation is used - e.g. Ionic 4 uses a page-based pattern rather than the usual Angular app.component.ts / app.component.html paradigm.

npm install -g cordova

cordova platform add ios
cordova platform add android





