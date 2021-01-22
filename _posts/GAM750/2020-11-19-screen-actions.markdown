---
layout: post
title: Screen Actions
date: 2020-11-19 00:00
published: true
---

# Final sprint requirement: Doors working as portals for teleporting

.. with visual representation to indicate a screen is a portal

At the moment, different combinations of specific hands + contrller-triggers, have a different action - see **[this post]({% link _posts/GAM750/2020-11-01-screen-panel-trigger-button-2.markdown %})** on the subject.

I have now discussed a change, where there is one touch - different hands have no seperate effect - **keep it simple**. Will keep using the trigger in conjunction with hand entering the collider.



A simple question to consider: when adding a screen display state - should I actually be updating an existing one instead? i..e StoreScreenDisplayState only adds to the array. Should I remove old ones - i.e. use RealtimeSet instead of array? This could, of course be done with a Realtime Array, but instead of actually removing elements, they can be set to on or off.

Probably just allow IsPortal to be part of the realtimeSet/Array state - this can then be set by the Stage Manager.

So, ultimately, the **stage mangager role** will be to 

* select a video clip and assign it to a screen in any scene
* select a live video feed and assign it to a screen in any scene
* select a screen in any scene and make it a portal to another scene
* set into motion an animation to transform a screen formation in any scene


