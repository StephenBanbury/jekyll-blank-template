---
layout: post
title: The Screen Panel Button Revisited
date: 2020-11-01 00:00
published: true
---

I have modified the screen panel's action as a _'button'_. Further modification, functionality and refinement to come...

A problem up until this point in time has been the tendency for the screens to react to the present of the players' hand in its collider when this has not been the desired effect, such as just getting the way of the screens as they move due to animation of formation changes.

I have now added the need to use specific hands in combination with the controller buttons in order to trigger specific actions.

* Left hand + left trigger = random screen formation change
* Right hand + right trigger = random video clip selection
* Left, right or both hands + left + right triggers =  open a portal allowing the player to exit the scene through the screen.

The latter option raises the screen's mesh collider, thus allowing the player to pass through. This is written into a coroutine and allows 3 seconds before the 'door' is closed again and access is once again denied. 

**NB** raising of the collider is because my initial attempts to disable it did not work, due to this also having the effect of disabling the script itself, thus preventing the completion of the coroutine, leaving the gateway open and rendering any further activity attached to the screen impossible. Raising and lowering the collider simply moves it out of the way temporarily, in the manner of a portcullis!
