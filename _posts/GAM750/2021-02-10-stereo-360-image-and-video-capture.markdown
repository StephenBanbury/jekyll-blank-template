---
layout: post
title: Stereo 360 Image and Video Capture
date: 2021-02-10 00:00
published: true
---

The intention is for **Not Near Enough** to be showcased at the 2021 **[National Student Drama Festival](https://www.nsdf.org.uk/what-we-do/our-yearly-festival/)**. Clearly, given the pandemic, it will not be possible to present the project in the usual manner, with real equpment and real people together in a real space. However, the intention is to create a 360 degree video capture from inside the virtual space. Here, I will explore possibilities for its creation.

An early 2018 **[Unity blog](https://blogs.unity3d.com/2018/01/26/stereo-360-image-and-video-capture/)** introduces a method to do this. 

>We are proud to announce that in 2018.1 creators can now capture stereoscopic 360 images and video in Unity. Whether you’re a VR developer who wants to make a 360 trailer to show off your experience or a director who wants to make an engaging cinematic short film, Unity’s new capture technology empowers you to share your immersive experience with an audience.

The solution is based on **[Google’s Omni-directional Stereo (ODS)](https://developers.google.com/vr/jump/rendering-ods-content.pdf)**.

The problem here is that I am using Unity 2020.1, which no longer supports the old XR (Activate the feature: Edit > Project Settings > Player > XR Settings > 360 Stereo Capture). At this stage I am not certain if this technique will work at all with Unity 2020.1. I expect this to involve some trial and error.

# However...

**Unity Recorder** is available via Unity's Package Manager. This allows recording of 360 video (along with other, more regular formats) in the editor. This appears to do the job that is required. I would still like to find a way to record 360 video from a camera (or, even better, multiple cameras) placed within the virtual environment, that captures each scene, including pre-prepared video, streamed video and all player-avatars as they enter and interact with the environment. This would preferably be during 'game play', rather than edit mode. Wouldn't it be nice if you could just select this from the 'share' menue in Quest Home, as an option when chosing to record, or to share, live stream/game-play.

# The Solution

Using the Unity package, *Unity Recorder*, in the Unity editor, I have been able to record 360 video footage from the main camera. It is, it seems, possible to select more than one camera, and I will explore this later. However, I used the Controller App to enter into the virtual space and placement was at the centre of one of the scene formations. I cued up a set of videos for a NNE student-created scene, started recording, and set the videos to start. Once I'd recorded a few minutes, I used *Google's 360 video metadata tool* - **[Spatial Media Metadata Injector](https://github.com/google/spatial-media/releases/tag/v2.0)** - to 'inject' the metadata required to represent the video in the correct format for publication, and uploaded it to YouTube and Vimeo.

**Still from raw 360 video**<br>
![Raw 360 video](\images\GAM750\360-capture-1.JPG)

<br>

**Trial 360 video**
<figure class="video_container">
  <video style="width:1120px;" autoplay loop muted>
    <source src="\media\GAM750\360-trial-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

The result is a 3D video that can be viewed on a regular flat screen using the mouse to move around, on a mobile device by moving the devices orientation in realtime, or using a phone and Google Cardboard to view a stereo version that reponds to movements of the head.

It works well. My only concern is the quality of the video - there does appear to be some pixelation that would be nice to avoid if possible. I will be examining the possibilities of enhancing the quality of the video, but for now, this is a good result with excellent potential.

**[View the video on Vimeo](https://vimeo.com/511245233)**

<br><br>

**'Raw' 360 video from the Unity editor**
<figure class="video_container">
  <video style="width:1120px;" autoplay loop muted>
    <source src="\media\GAM750\360-1-compressed.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

<br><br>

**Metadata-injected 360 video**
<figure class="video_container">
  <video style="width:1120px;" autoplay loop muted>
    <source src="\media\GAM750\360-1-compressed-_injected.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>



