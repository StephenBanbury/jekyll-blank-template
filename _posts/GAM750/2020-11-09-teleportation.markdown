---
layout: post
title: Teleportation In Action
date: 2020-11-09 00:00
published: true
---

# Finally! Teleportation is working

It's taken a bit of time getting here - I estimate I [**spent the best part of two days**]({% link _posts/GAM750/2020-10-27-multi-space-4.markdown %}) trying to get teleportation between 'scenes' working - but now it's finally up and running.

The solution turned out to be fairly simple:  

  disable both the OVRPlayerCharacter and the OVRSampleScene => Move the player => re-enable the OVR objects

I found this only worked if enough time was allowed surrounding the various part of this series - without a delay which the actions take place, the player appears to get stuck and no teleportation happens. For this reason, **I placed the method into a coroutine**, which adds a short delay after the OVR objecs have been disabled, and then another delay after the teleport itself has occured, but before the re-enabling of the OVR objects.

I added a sound effect for teleportation to add to the experience. When time allows, I will look at some kind of visual effect too.. perhaps putting a 'box' over the player's head for those seconds during teleportation - I could have fun with the lights and graphics inside the box!

## STOP PRESS!

It's still not working correctly. 

I can teleport between a few scenes with no apparent problem, but then, suddenly, the next location will be outside the intended scene, i.e. not true to the coordinates given. At its worse, I could find myself some distance away from the main play ares, or even off the groung plane entirely.

**Teleportation issue**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\teleportation-issue-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>


# Fixed!

The problem was that the player was nested within a container game object. It was this object that was being teleported to new locations, rather than the player object itself. It seems the relative coordinates of the game object, **local** to the containing object, were becoming increasingly distorted the more moves that were made. Now, having removed the player from the container and applied the spawn point teleportation coordinates directly, the problem appears to have vanished.
 
 **Teleportation working**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\teleportation.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

