---
layout: post
title: Video Streaming Experiments
date: 2020-08-07 01:00
published: true
---

# Early attempts at setting up a server

As can be seen here **[Building A WebRTC Web App]({% link _posts/GAM750/2020-07-27-webrtc-web-app.markdown %})**, I have build a simple **node.js** server using Express. I considered hosting this, or something similar - perhaps a .NET server - in AWS or Firebase. Could I still use PeerJS as a STUN/TURN server? I'm still new to this so, even though I'm picking up new stuff contiually and gradually piecing it all together, I'm uncertain how to fit it all together. I know I can learn as I go, but it's quite a lot to get to grips with in a short space of time - there is little scope for taking the wrong route and backin up.

# Kurento media server

I began looking at setting up a **[Kurento media server](https://www.kurento.org/whats-kurento)**, which could be hosted as an instance in a **[Docker container](https://hub.docker.com/r/kurento/kurento-media-server)**. This is a super idea and is enthusiastically supported by Alcwyn Parker, the Masters Degree course leader and my research tutor on this project. However, time is, again, a major issue - for both of us. We did spend some time working on sett up such a stack, but eventually it seemed sensible to work with an out-of-the-box WebRTC solution we were aware of - **[Agora](https://www.agora.io/en/)** - as long as research showed it to have the right potential. 

# Agora

* Uses WebRTC
* First 10,000 minutes free every month (so likely to remain free for the kind of use we'll be putting it to)
* Pay As You Go [pricing](https://www.agora.io/en/pricing/)
* Cheap 
* Simple to set up
* Can stream voice and video

The Unity asset contains a couple of sample scenes that are fairly easy to set up. I had some problems building the scene in order to spin up multiple instances - necessary so that multiple connections can be made - as the documentation is not 100% idiot proof, but with a bit of **tenacity** and patience I got something very promising working.

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\agora-test.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

The Unity asset is for 'live interactive video streaming'. This is geared towards one single main video channel at a time streamed to multiple locations. There is another option for 'democratic' open channels where all can communicate at the same time to all others. I do not this the latter option will be necessary for us, because we will be streaming single performers into the Unity space.

It was great to see the video images being displayed directly onto textures in Unity, such as the cube - this should prove useful and time-saving.

# Conclusion

**Agora** looks to be the way to go, at least for the time being. I would prefer to be building my own server and exploring the use and potential of some exciting new technologies in a more 'raw' form - partly for my own personal curiosity and learning, but also for an increased self-contained, stand-alone stack that does not rely so much on external products. Perhaps this could be a later development of this project once the initial objectives have been met. For now, the precious resource of time is a prime consideration.

