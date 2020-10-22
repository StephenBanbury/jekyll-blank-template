---
layout: post
title: The Performer App 2
date: 2020-10-01 01:00
published: true
---

# Problem solved

I created a copy of the main VR scene and reset the UUID of the Normcore Realitime View (Script) attached to the MediaDisplayManager GameObject. 

The MediaDisplayManager exists to house the management classes that control media-related objects and actions, such as the screen panels, e.g. video screen selection and media assignment, the Agora video streaming controller and interface, and other related management tasks - simply, a kind of Game Manager but specifically for controlling media in the widest sense. 

I then replaced the VR player with another, exactly the same but using an 'invisible' copy of the OVR player, i.e. I disabled the body and just kept the camera and Realtime components to persist the player in the multiplayer environment. I added a Rigidbody and a script to allow control via the keyboard rather than VR. 

When this scene is built, it must have the VR Plugin Management disabled in Player Settings. This then creates an exact copy of the VR scene, in the multiplayer environment, but the player is invisible and unable to affect any change or force on the space - a ghost. When a PC build is created it runs on another PC - the VR character(s) in the space can be viewed along with the results of their actions, i.e. screen/video/formation selection and assignment changes etc., whilst the invisible player can move around using the keyboard.



