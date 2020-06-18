---
layout: post
title: What Am I Doing? Part 2
published: true
---

## Attempts at finding a way to make this game compelling

# Leader board

Tapping into the competitive nature of (most) human beings, and the reason for the actual existence of (most) games (that's a statement I will need to back up with some sound research!), it may be worth developing the _competitive_ side of the game. Introducing a scoring system and a subsequent _leader board_ could achieve this.

As I'd like to incorporate a multi-player aspect to this game at some point, this could be looked at from a number of perspectives. Competition between individuals playing individually, is one thing, but there could also be competition between individuals playing as a team. It may be that individuals get rewarded for being more successful than their co-player, but is could also be that individuals get rewarded for being more team-oriented. These are concepts I will further explore.


# What to do when a disaster scenario has been fully deployed?

1. **Replace with a new mission:** I have played with ideas around replacing a completed mission with a new one. This involved selecting a report from the list - i.e. the list that a random selection is taken from at the start of the game - and replacing the completed report.
2. **Close down the screen:** with style! Screen spins round, shrinks and vanishes! Will need suitable sound effects for this. I imagine this being tied up with the points scoring system, whereby a completed mission is worth a large amount of points, to be added to the points scored by assigning resource objects.

# Wind zone

An increasingly gusty wind zone to blow resources off course. I could use Unity's 'wind-zone' object or, as I did in the _disaster scenario_ scene of my prototype, define a large collider that applies directional forces to objects that enter within.

**GitKraken 'Glo' Kanban Board**
![GitKraken 'Glo' Kanban Board](\images\gitkraken-glo-board.jpg)

# Haptic feedback

As I want to include some tactile feedback for the user when picking up objects and touching buttons and screens etc., as usual I searched the internet for documentation, advice and tutorials. As is often the case, the Oculus documentation is limited and did not examine a real-world scenario. The instruction provided is to use 

    > static void OVRInput.SetControllerVibration(float frequency, float amplitude, Controller controllerMask)

[Oculus documentation: Unity Haptics](https://developer.oculus.com/documentation/unity/unity-haptics/?locale=en_GB)

    so calling > OVRInput.SetControllerVibration(1, 1, OVRInput.Controller.RTouch); 
    should do the trick. Except it is very uncontrollable. I want a short burst and this lasts for 2 seconds. This would mean I would have to contrive a a short burst using a coroutine in order to instigate a short delay before stopping the feedback (i.e. with zero values for frequency and amplitude). 

Again, as it often the case, further searching found better, more usable, solutions. In particular one from Valem (Valam is a very handy guy to have around, as I've mentioned elsewhere) provided a thoughtful and useful solution. His can either use a sound file to control the nuances of the haptic feedback or can take parameters that define the frequency, duration and strength in a much more controllable way when compared to Oculus's own API. 

[Valem: How to make a VR game in Unity - Part 5 - Controller Vibration](https://www.youtube.com/watch?v=9KJqZBoc8m4)

![The haptic parameter](images\haptic-valem-1.jpg)



