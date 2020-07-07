---
layout: post
title: Building Multiplayer
published: true
---

## Unity XR Integration & Mirror

[Good Mirror totorial series, but not VR specific](https://www.youtube.com/watch?v=5LhA4Tk_uvI)

I could only get to the point that my XR Rig (i.e. my player character) could appear as multiplayer clients, but I have so far not got to the stage where each client can see the other in the same space. 

There is a distinct lack of documentation for using Mirror, less for XR Integration, and zero (it seems) for XR Integration multiplayer solutions!

I am keen to follow this route - it is my chosen one for reasons given elsewhere - but may have to resort to older tech and methods. Rather than spend too much time figuring this particular stack out, I now intend to look into using Oculus Integration (which I already know works, from experience) and Photon (which is mature, tried and tested and is better documented than Mirror).

[Video showing XR and Mirror]

## Unity, Oculus Integration & Photon PUN

An old tutorial aimed at the Oculus Rift - hopefully Oculus Link will allow development to work seamlessly on the Quest: [Tutorial - an oldie, but hopefully a goodie!](https://www.youtube.com/watch?time_continue=3&v=CraH51-_xJo&feature=emb_logo)

A non-VR tutorial series on PUN 2 that is pretty comprehensive, by [Info Gamer](https://www.youtube.com/watch?v=02P_mrszvzY).

## Is there a better way?

Is using one solution for the multiplayer network and another for streaming data and video the best option?

I'm not sure..

Could something like WebRTC do it all? I assume it won't have the specific multiplayer scripts / API included by the others, but has anyone done somthing like this? Whether it could be **made to handle multiplayer** functionality may be missing the point. If it can be made to do so, **do I have the time?** to implement it?
This, I doubt very much.

[webrtcH4cKS: ~ Gaming with the WebRTC DataChannel – A Walkthrough with Arin Sime](https://webrtchacks.com/datachannel-multiplayer-game/)

![WebRTC multiplayer data channel](/images/gam750/webrtc-multiplayer-1.JPG)

This is an interesting discussion about using WebRTC for multiplayer games. It is possible. But this is JavaScript. Making it work for Unity is another thing entirely. The Unity package may manage everything needed, but it would take a deep dive to find out how. 