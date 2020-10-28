---
layout: post
title: Multispace 3
date: 2020-10-25 00:00
published: true
---

# Controlling player and actions within multiple scenes

Spawning scenes, including screen formations, is just the start. How do you control the screen formations and the video projections and live video feeds for each individiual screen?

One line of enquiry, and the first option I tried, instantiates the selection control panel into the same starting scene as the player. The idea would then to ensure it is instantiated in the other scenes, with the player, when the player moves into them. 
This is a method I could end up working with.

Another option, and the second I am trying, is to instantiate the panel in all of the scenes (along with the audio source and lighting). The panel will probably only be visible to the player - each player can own their very own panel and show and hide it as they please (or it may end up being discarded altogether).

The difficulty then, with either of these options, is to ensure that: -

1. all actions cause an effect on the specific scene in which the player is situated
2. all effects are permiated through to the multiplayer models and then to each player instance


# Update

I have managed to set the screen formation animation to occur for a specific scene when the button for that formation is tapped on the panel associated with that specific scene. This is done by finding the parent scene of the selection panel and sending it to the tweening method. Remember, the tweening, along with spawning, is already able to pinpoint which scene to act upon - this has made further development - and my life - much simpler!

I am now concerned that this may be difficult to translate into the multiplayer environment. This will be the next stage of development.