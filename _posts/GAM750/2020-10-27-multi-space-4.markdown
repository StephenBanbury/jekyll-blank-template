---
layout: post
title: Problems With Teleportation
date: 2020-10-27 00:00
published: true
---

# Problems with teleporting the player

I have been having great difficulty with the function of teleportation of the Oculus PlayerController from one space/scene to another.

I would have thought that would be reasonably straightforward, in the same way as it is for spawning inanimate objects, such as screens and selection panels, by simply changing the transform associated with the player. I have set up spawn points and placed these within the individual scenes, then attempted to take their Vector3 positions and applied them to the player's. However, I end up moving in an outrageous manner, often ending up outside the area of the scenes, or even off the floor panel altogether, leading the player to end up in freefall.

I have attempted placing the player within an empty GameObject, as well as stand-alone, but the same result ensues. 

This has been immensely frustrating. 


# Figured out the issue (to an extent) but do not have a solution

I set up a marker - a red capsule - and instead of applying the spawn point positions to the Player, I applied them to the marker. The marker moved around the environment perfectly and as should be expected! So the problem is with the player.

**'Spawning' the player**<br>
![SpawnPlayer](\images\GAM750\spawnpoint-method1.JPG)

This is what it looks like in the environment with scenes. You can that sometimes the player is just shifted a few feet, other times the player is moved much further, but nowhere near the spawn point, and even off the floor plane.
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\spawnplayer-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

Here you can see quite clearly the layout of the environment with no screens to obscure it
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\spawnplayer-2.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>


**'Spawning' the marker**<br>
![SpawnMarker](\images\GAM750\spawnpoint-method2.JPG)

Here you can the red marker - which is a simple 3D object with no VR special characteristics - move and spawn as expected, whereas the VR player gets pushed around in an apparently random fashion.
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\spawnmarker-2.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

I experimented with using the Normcore VR Player, which is simply an avatar with the Normcore Realtime components attached to allow it to work in multiplayer, and is cloned during game-play, and the 'regular', local player, that contains the camera rig (so naturally, that would appear to be one to use). 

I also deactivated the Normcore-enabled player / avatar set-up altogether, and tried out a simple, basic, vanilla Oculus OVR PlayerController. This had exactly the same effect. 

To illustrate what is going on: -

**The spawn point's location, where the player is supposed to be positioned (0, 1, 20)**
![SpawnMarker](\images\GAM750\spawnpoint-error-inspector-2.JPG)

**The values being applied to the player's transform (-0.8, 0.4, 20.2) - near enough to the spawnpoint's exact location**<br>
![SpawnMarker](\images\GAM750\spawnpoint-error-console-1.JPG)

**The location the player actually ends up! (39.8, 0, -20.8). Go figure!**<br>
![SpawnMarker](\images\GAM750\spawnpoint-error-inspector-1.JPG)

<br>
**The x coordinate is way, way out! How can this be?!!**



It's difficult to know where to go next with this! I wonder if it would be worth considering attaching the player to another object and using motion to move it to another space - as simple repositioning of a containing object had the same erroneous effect.

First port of call, though, will be to research, to try to find something about this online.

As The Terminator once famously said, **I'll be back...**