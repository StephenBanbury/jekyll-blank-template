---
layout: post
title: The Controller
date: 2020-11-26 00:00
published: true
---

# The controller app-

This should be fairly straightfoward but it is proving to be far from that!

I had built the original demo to use **OSC messaging over HTTP**. However, I decided to move away from this idea and to turn it into a **Normcore project**, where Realtime models are used to update the VR client environments directly. However, they are currently not updating. The Realtime models are updating and firing events that are recognised by the local client and any other controller app clients, but the events are not being picked up by the VR client listeners and, therefore, nothing is happening.

I have asked for help on the **Normcore Discord** channel and, after the first response on a slightly different issue, pointing out the need to enter different rooms in order to prevent the controller app attempting to instantiate the VR prefabs, none has been forthcoming. The fact that the controller app is trying to copy the VR app's environment when the room names are the same, suggests there is a connection, but the custom Realtime models are not on the same page, so it seems.

I will continue building the UI and hope that I can wire it up at some point. If necessary, I could always go back to OSC and hope that I can get the OSC clients to communicate over the local network, or I could send text messages via Agora. Both these options could be made to work, I feel, but are not the ideal solution.

# It's all about rooms

* **NB** With help from Max (a Normcore founder) and another poster, I discovered that it is all about **Rooms**. The solution is to have a single App ID and then a room for the VR players and a room for the controller app, whilst maintaining and sharing the same Realtime data-stores for components that are shared between both, used by both VR players and the controller app. Seems simple once the penny has dropped!

