---
layout: post
title: Video Streaming
published: true
---

I want to stream video and other media and data into my Unity-created VR experience. 

**_How can I do this?_**

Reading around the subject of sockets, both in general and specifically with regard to Unity: -

* # [web.dev](https://web.dev/websocketstream/)

**[WebSocket API](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)**: a JavaScript interface using the **[WebSocket protocol](https://tools.ietf.org/html/rfc6455)**. <br>

Opens a two-way open interactive communication session between browser and server. Does not require server polling.<br>

**[Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Streams_API)**: JavaScript API to access streams of data chunks. Reading/writing speed is regulated by the concept of **[backpressure](https://developer.mozilla.org/en-US/docs/Web/API/Streams_API/Concepts#Backpressure)**.<br>

The WebSocket API cannot apply backpressure, so can get overwhelmed when messages arrive faster than they can be handled. The solution is the **WebSocketStream API**.


* # [StackOverflow](https://stackoverflow.com/questions/42717713/unity-live-video-streaming)

This person has a minor problem with a solution they have built in Unity. They are sending images, but much of the principle should be the same. Of course, it's the solution I'm interested in studying.


* # [Unity forum](https://forum.unity.com/threads/stream-video-through-network.464693/)

* # [Playing video from url](https://answers.unity.com/questions/1363049/does-videoplayerurl-supports-playing-live-video-fr.html)

<br><br>
**.. continue - there are many more links to go here**

<br>
<hr>
<br><br>

# Out-of-the-box options

**[WebRTC](https://webrtc.org/)**
* Open source (so free!)
* Mature as non-Unity platform
* Unity package **_should_** work with both Oculus Link (NVIDIA codec) and untethered/Android (Vulkan/OpenGL)
* Appears to have recently been [embraced by Unity](https://blogs.unity3d.com/2019/09/17/stream-high-quality-real-time-graphics-through-your-browser-with-our-new-webrtc-framework/) as their defacto tech in the area of streaming

**[Agora](https://www.agora.io/en/)**
* Free for low use only
* Pay As You Go [pricing](https://www.agora.io/en/pricing/)
* Simple to set up
* Can stream voice and video

**[Genvid](https://www.genvidtech.com/)**

Appears to have a functionality set that is close to what could be required.  There is a [pricing/licensing structure](https://www.genvidtech.com/licensing/), that depends on individual unique viewers per month. I'm not quite sure how this would work in the kind of scenario I'm thinking of.

