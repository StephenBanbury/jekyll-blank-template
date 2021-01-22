---
layout: post
title: The Controller App 
date: 2020-12-03 00:00
published: true
---

It's starting to come together.

More efficient: - 
* not attempting to update screens if they already are showing the correct video
* not updating individual screens and then adding to realtime array - now only realtime array is updated, which fires the event in the other clients and updates their arrays.
* Use local 'buffer' for screen media, which is synced locally with RealtimeArray. If an item exists in the RealtimeArray and in the buffer, there is no need to process it at all when a model is added by a remote client. If a player joins late, their local buffer is compared to see what is missing.
* Added screen portal - also uses a buffer. Portal can be set to on for any screen in any scene. Setting it to 'off' is a problem at the moment, as RealtimeArray does not have a 'didChange' event. There must be a way, but for now I'm having to set it to off locally, and it updates remotely only when another portal is added because a new model is added to the array.

All in all, things are much quicker, with little lag, and screens no longer go blank before having video assigned.

Also: -
* Added ability to move and rotate overhead camera.
* Added VR player, which connects to the VR player's room and thus is instantiated by remote VR clients and shown in the controller app. This is really very interesting, giving a feeling of **'god-like'** control over the VR players' world!
* Made players emissive yellow for clarity
* Instantiating buttons - started with Agora video stream channels as they are created and destroyed.


    
    