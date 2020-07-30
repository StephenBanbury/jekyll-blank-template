---
layout: post
title: Streaming To And From Unity
date: 2020-07-25 15:00
published: true
---

# The requirement

I need to find a way to take data from a device and stream it into my Unity scene.

An example would be taking video from a webcam or a mobile phone camera, creating a data stream to which a Unity script can subscribe and then display the streamed video onto a texture within the scene. 

Another, perhaps simpler example, would be to take numeric 2D positional data, manipulated on the screen of the extertanl device, and stream that to Unity.  The data can then be used to control the position of an object within the scene.

Audio would be another, allowing a stream of audio data from the external device's microphone to enter the Unity scene and be heard by the players via the audio mixer.


# Thinking about options

Would it be best, or feasible, to create a room in the Unity project that can access the device's camera resources, and then to create a build for each platform - i.e. Android (can be the same build as for the Oculus quest), iOs and Windows.

Or could the unity project be cloud-hosted, allowing users to connect via the internet. The cloud app would need to be able to access the device's resources across the internet, much like Zoom or Skype etc.

An alternative may be to create a web app that can run in a browser - perhaps raw JavaScript or an Angular/Vue/React etc. app, which can access the device's resources and stream via a socket to a server. The Unity project can then connect to a socket on the server and subscribe to the datastream.

Other than these options we could be looking at either a cross-platform option, like Flutter or Ionic, or multiple Native apps.

# Random research

* **[StackOverflow](https://stackoverflow.com/questions/37100900/unity-processing-data-stream-from-socket)**: Unity Processing Data Stream from Socket.  This is an interesting question asked on StackOverflow and it leads to a **potential solution** for setting up a TCP client in Unity: **[Simple socket server in Unity](https://stackoverflow.com/questions/36526332/simple-socket-server-in-unity/36526634#36526634)**

* **[Another on StackOverflow](https://stackoverflow.com/questions/46564222/how-to-send-and-receive-tcp-messages-while-streaming-video-unity-and-socket-ne)**

* **[And another...](https://stackoverflow.com/questions/42717713/unity-live-video-streaming/42727918#42727918)**

* **[... and guess what...](https://stackoverflow.com/questions/17719541/writing-and-reading-using-socket)**

* **Mozilla:** **[The WebSocket API (WebSockets)](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)**
  * **[Writing a WebSocket server in C#](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_server)**
<br><br>

* Another possible option could be to re-use the code already implemented in my **[C# TCP/UDP multiplayer experiment]({% link _posts/GAM750/2020-07-11-client-server-tutorial.markdown %})**.  As it is basically about sending and receiving data between clients via a server, in a sense it is already all in place. I'm tempted to combine this with what I could learn from the above Mozilla WebSocket documentation and to build the solution from the ground up.
  
* **[WebRTC](https://webrtc.org/)**: I keep coming back to this - it's potentially the all-encompassing solution, covering browser, native, Unity - both client and server, both directions possible (or so it would seem). 
  * **[My earlier post on WebRTC]({% link _posts/GAM750/2020-07-02-webrtc.markdown %})**
  * **[Microsoft's WebRTC project](https://microsoft.github.io/MixedReality-WebRTC/manual/gettingstarted.html)**, including a library for **[Unity](https://microsoft.github.io/MixedReality-WebRTC/manual/unity/unity-integration.html)** and a **[Unity tutorial](https://microsoft.github.io/MixedReality-WebRTC/manual/unity/helloworld-unity.html)**.
  * **[Unity documentation](https://docs.unity3d.com/Packages/com.unity.webrtc@2.0/manual/index.html)**: includes links to a **_Tutorial_** and **_Reference_** for **_Video_**, **_Audio_** and **_Data_** streaming.
<br><br>

* **[Unity Render Streaming](https://github.com/Unity-Technologies/UnityRenderStreaming/blob/release/1.0.0/Packages/com.unity.template.renderstreaming/Documentation~/en/tutorial.md)**: streaming video out from Unity project using **WebRTC** - I'm not sure just yet how useful this could be - whether it is just from the editor or from a live build. Either way, it looks interesting.

# Unity Assets

* **[FMETP](https://assetstore.unity.com/packages/templates/packs/fmetp-stream-143080#reviews)** This asset may do the trick on a number of scores - video in and out.<br>
  **[FMETP - Unity forum](https://forum.unity.com/threads/release-fmetp-stream-all-in-one-gameview-audio-stream-udp-tcp-websockets-html.670270/)**
  
  This certainly does look like an interesting solution. The devlelopers are very much on the ball, judging by the various queries and reqests, so even if if it not directly perfect for my use, it should be possible to work with the developers in finding a solution. 
  However, even as it is, it could provide a solution to my requiments - [see here](https://answers.unity.com/questions/1509753/stream-live-video-feed-into-unity.html).

* **[Using Socket.io and Unity 3D To Build Multi-User Experiences](http://innovativeteams.net/using-socketio-build-multi-user-experiences/)** This makes use of the Socket.IO for Unity (see above).

* **[OpenTok (2017 post)](https://tokbox.com/blog/add-opentok-live-video-chat-to-unity/)**<br>
  **[OpenTok (2019 post)](https://tokbox.com/blog/unity-opentok-take-two/?utm_source=rss&utm_medium=rss&utm_campaign=unity-opentok-take-two)**
  
* **[Agora](https://assetstore.unity.com/packages/tools/video/agora-video-chat-sdk-for-unity-134502)**
  Unity asset - another out of the box solution. It is [well priced](https://www.agora.io/en/pricing/) and could be very useful. I'd rather build my own though...

* **[WebRTC Video Chat asset by Because Why Not?](https://www.because-why-not.com/webrtc/)**: This costs (about £100) for the asset.

# Other

* **[liveswitch cloud](https://www.liveswitch.io/)**: has monthly pricing - $19 plus per minute payment

* **[Spitfirex86](https://www.nuget.org/packages/Spitfirex86/)**: NuGet package - for .NET applications rather than specifically Unity.
  
* **[Amazon Kinesis Video Streams](https://aws.amazon.com/about-aws/whats-new/2019/12/amazon-kinesis-video-streams-adds-support-for-real-time-two-way-media-streaming-with-webrtc/)**: _"Kinesis Video Streams includes a WebRTC signaling end-point for fast peer discovery and secure connection establishment. It includes managed Session Traversal Utilities for NAT (STUN) and Traversal Using Relays around NAT (TURN) end-points for real-time exchange of media between peers."_ You pay for what you use - looks reasonably priced.
  **[How it works](https://docs.aws.amazon.com/kinesisvideostreams-webrtc-dg/latest/devguide/kvswebrtc-how-it-works.html)**

* **[Set up TRUN/STUN signal/relay server on AWS EC2](https://medium.com/@omidborjian/setup-your-own-turn-stun-signal-relay-server-on-aws-ec2-78a8bfcb71c3)**: could be very useful

* **[Firebase + WebRTC](https://github.com/webrtc/FirebaseRTC)**
  **[Getting started](https://webrtc.org/getting-started/firebase-rtc-codelab)**

* **[WebRTC Samples](https://webrtc.github.io/samples/)**: a collection of small samples demonstrating various parts of the WebRTC APIs










# Moving forward...

I have been trying to find a simple, straightforward, way of introducing WebRTC into a Unity project. However, I have had trouble whichever way I've turned. The Microsoft package looks interesting, but my implementation via **NuGet** did not introduce the Unity sample scripts and components as described. The full package implementation (i.e. before even considering the implementation of the WebRTC scripts etc. and getting a working solution up and running) could, I suppose, be studied in detail, but it looks pretty complex and I'm not sure that spending too much of my time doing so would be time well spent as there is no certainty that the result would be successful.

The Unity documentation itself is not very complete, in fact I'd characterise it as being sparce. It seems to explain snippets of code as though you already have them set up in your project, without explaining how to actually set them up in your project or give a wider context to them. It appears to be another case (I come across this fairly often) of documentation written by developers who assume you have been on the journey with them, but have been easily distracted.

I also tried following the Unity Render Streaming tutorial but, less than a year on, it is already out of date. I had trouble with the latest releases being quite different in terms of file content and the resulting WebRTC templates for Unity were not in line with what was being demonstrated in the video. I'm sure there are more tutorials out there, but for now **I feel that my time would be better spent actually learning about WebRTC in general, rather than as a Unity plugin**. Once I have the basics, and really understand them, I should be able to apply them more easily to my specific Unity test-case.

