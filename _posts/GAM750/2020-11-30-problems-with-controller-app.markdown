---
layout: post
title: The Controller App - Problems, Issues, Headaches
date: 2020-11-30 00:00
published: true
---

This is the non-OSC version. Should I have stuck with OSC? The fact that it did not appear to work for the testers in the studio made me a bit queezy about perservering for too long. The Idea of hooking it up with Normcore was quite appealing, as I imagined 'simply' adapting the existing VR controller panels to work as a stand-alone app, controlling the whole virtual space.

Original UI-only app was not firing updates to other clients.

I copied the code-base from the VR app into a new project, brought in the original 2D controller UI scene, and wired it all up. This is very promising. Events are firing in the other clients - although a lot of work will need to be done to make this work seemlessly and slickly - and, probably best of all, I can superimpose the 2D UI on top of a scene created by an overhead camera displaying the whole space. It would be nice to be able to control the camera too - this is for another day!

Problems with delay - the delay on the VR client is unacceptable. 


Some duplication was removed - originally, when a video clip or stream was assigned to a screen, the action would take place and the realtime datastore was updated for that specific individual action, meaning that the clients would also be updated with the specific individual action. 

As I am now using RealtimeArray for the full set of screen states, this is no longer necessary. Any changes that occur within the array are automatically updated by all clients. So, there has been a duplication of effort. The change I have no made does away with the individual actions, and only the RealtimeArray is used. It should be possible to further free up resources by removing entirely the old Realtime models for selecting individual video clips/streams and screens on which to display them. I will also seek to do this with teleport portal selections. Scene formations can remain for now.

This does appear to have sped things up, but screens are still going blank before updating with the entire RealtimeArray. I will need to work out why this is happening and how it can be prevented. Also, thinkgs to seem to slow down over time, suggesting perhaps a memory leak or lack of disposing / recycling of objects. 
