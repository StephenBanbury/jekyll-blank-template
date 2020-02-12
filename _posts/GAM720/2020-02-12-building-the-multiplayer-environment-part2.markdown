---
layout: post
title: Building The Multiplayer Environment | Part 2
published: true
---

## Building and animating a player character

The tutorial has a useful introduction to [building and animating the player character(s)](https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/player-prefab). This is not PUN-specific so comes as an unexpected but welcome addition, as character animation is something that I will need to look into sooner or later.

The robot prefab is provided for demo/experimental purposes as part of the Photon PUN 2 asset download, as are the animations required to get him moving (running, swinging arms etc.). These need attaching to the robot GameObject along with a character controller and the usual collision detector etc. The tutorial provides help on this and setting the animator in motion. However, I am clear that I will need to learn how to create 3D objects like this, as well as build character animations. 

**Running and jumping**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-3.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

**Running and jumping.. with style!**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-5.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

The robot character is not easy to control, being limited in its ability to stop, turn without running forwards, only jump in a single, slightly 'parkour' style and it can only run at a certain speed. Of course, there is much more that can be done to improve things. This 'demo' does indicate, however, how much more work would need to go into creating a more usable animated character that is enjoyable to play with. 