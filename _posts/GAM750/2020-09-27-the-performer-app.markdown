---
layout: post
title: The Performer App
date: 2020-09-27 01:00
published: true
---

# How should the performer experience the VR space?
I had been wondering for some time how I would approach the issue of enabling the performers, who are streaming live video into the VR space to be projected onto the panel screens, to **also be able to see what is happening within the space**, where audience members are located, where they are looking, how they are moving; the screen formations and how they morph into different shapes; lighting; other performers and where they are beging displayed etc. 

**Rendering video via WebRTC**<br>
I had assumed that I would need to stream video, or _volumetric capture_, from the environment to be displayed, for example, on a browser or some other display. I imagined this would make use of WebRTC in a similar way as streaming live video of a performer into the VR space. I'm sure it would be possible, but it would be time consuming - not something I would relish after having already spent a significant amount of effort and time on the stack put in place thus far. However, it would certainly be an option for further development if required - Oculus has developed a **[streaming solution](https://forum.unity.com/threads/unity-render-streaming-introduction-faq.742481/)** (the GitHub repository is **[here](https://github.com/Unity-Technologies/UnityRenderStreaming))**, so it's not unprecedented.

**Sending positional data to the performer/client**<br>
Then I began to think of streaming pure location data for performers and screens etc to a separate app, where they could be used to map the space in real time.

**Joining the performer into the multiplayer space**<br>
However, the most immediately straightforward option would also seem to be potentially the most useful: to join the performer into the multiplayer space as an invisible player, who can roam around with absolute freedom, but who's presence cannot be perceived by the audience. The performer would not be experiencing the space through VR, but on a 2D flat screen, and controlling their movements using keyboard or mouse. I did briefly experiment with just having an overhead camera above the space, but this was soon replaced with the more immersive option of being in the space itself.<br>

**Overhead Camera**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\overhead-camera-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>
<br>

**Performer 'in space'**<br>
Here the performer is in the space with a single VR player (i.e. audience). This is what it could look like when it's working - however, I am currently having some issues with Normcore allowing this to happen - it sometimes crashes out, loses connection, or freezes for the performer app. It may be that there is not enough separation, somehow, between the player, their Normcore 'realtime' player, their Oculus avatar.. or at least somewhere in there there is an issue - tracking it is proving difficult. But this video at least shows what could be possible!

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\performer-space-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

 **And here's the 'error'**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\performer-space-err-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>