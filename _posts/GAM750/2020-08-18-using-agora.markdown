---
layout: post
title: Using Agora
date: 2020-08-18 01:00
published: true
---

# Progress update
I have not posted for more than a week now, and this is due to the fact that nearly all my dev time (there has been family time too, or I'll end up with only dev time in my life - not a great prospect!) has been getting to know Agora and adapting the slightly haphazard demo material for use in my own VR app. There have been frustrating moments where things just do not work as you'd hope, but there has never really been a moment when I've thought "this is just never going to work", or "if this is going to work, then it's going to be more hassle than it's worth!". But I have continually been aware that it may be a laborious process, and this has been the case.

# What?! Just streaming?!

I initially set up screens to which I allowed the attaching of Agora's _VideoSurface_ component class. Once this was working, I needed to add back in the ability to diplay video clips. To this end I have a general 'media' class that covers both (and will cover any new) media types. Each screen object has attached, as a child, the already-existing screen object, that includes a VideoPlayer for video clips, and now, also, a canvas, to which an Agora VideoSurface can be dynamically attached as and when a stream is created and assigned to the display.

To the Normcore multiplayer model I therefore needed to add another variable representing the selected video stream. I can now select either a pre-loaded video clip or a video stream provided by an external client device's camera, and then assign it to a specified screen.  Depending on its type, the media will be displayed as a video clip by the video player or a video stream by the Agora video surface. If either a video or a stream is selected, followed by a display screen selection, the Normcore model triggers an event that informs all other clients to also select the same media and assign it to the same display screen.

Buttons to select specific video streams provided by Agora clients are dynamically created as each client joins the room. As they join, they are added to the client list (of AgoraUsers). Clients are never removed, but if they leave the room they are marked as such by a _LeftRoom_ property.  Each is assigned an ID that is used to select the specific video stream.

I am using a simple client app, based on the Agora demo, to provide a portal for external clients to join the room and create a video stream. This app uses the same Agora ID as the VR app (where streams are displayed) so streams are seen by the VR app, along with all other clients. 

**Streaming and playing local videos to selected screens**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\streaming-video-to-different-screens-2.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

# Problems

1. Currently, when a new VR app instance is created, this is viewed as a new client by the other clients, including those that are other instances of the VR app. Therefore, an Agora stream is created for each instance and appears as a new client, including a new select button, in the VR environment. I need to find a way to treat each of these as 'dead' streams - they should not appear at all. The VR users should only receive streams to be displayed. This may be different when the app is build for Android - I have not tested this yet - but when run as a PC app and tested via **Oculus Link**, the PC's camera is added to the stream pool.

2. **This has been fixed, but I'll keep the following for the record**: 
   I'm seeing problems where one or more of the video feeds is freezing. This does not happen straight away, but after adding more and playing with how they are routed to different screen destination. I'm not sure if this is something that is to do with streaming/bandwidth performance, or similar, or something to do with the way the Unity Agora asset works. It could be that only one live stream is allowed at a time, although my observations in a previous post would suggest that this should not be a problem:

    >The Unity asset is for 'live interactive video streaming'. This is geared towards one single main video channel at a time streamed to multiple locations. There is another option for 'democratic' open channels where all can communicate at the same time to all others.

    Of course, it could be that I have misunderstood the documentation, and the difference between **_[Voice Call](https://docs.agora.io/en/Voice/product_voice?platform=All%20Platforms)_** and **_[Live Interactive Video Streaming](https://docs.agora.io/en/Interactive%20Broadcast/product_live?platform=All%20Platforms)_**. I will be examining these descriptions closely! This is something that I very much hope is not the case, because there is no Unity asset for Void Call!

**Note**.. the issue turned out to be nothing of the sort and has now been fixed. I needed to ensure that any existing Agora video surfaces would be re-used if any new streams were to be displayed on its screen, i.e. replacing the existing stream. Previously, I had been destroying these existing surfaces and then creating a new one. 

**Streaming and playing local videos in multiplayer mode**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\streaming-video-multiplayer-3.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>


