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


