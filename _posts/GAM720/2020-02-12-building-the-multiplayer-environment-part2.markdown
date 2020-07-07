---
layout: post
title: Building The Multiplayer Environment | Part 2
published: true
---

# Building and animating a player character

The tutorial has a useful introduction to [building and animating the player character(s)](https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/player-prefab). This is not network-specific so comes as an unexpected but welcome addition, as character animation is something that I will need to look into sooner or later.

The robot prefab is provided for demo/experimental purposes as part of the Photon PUN 2 asset download, as are the animations required to get him moving (running, swinging arms etc.). These require attaching to the robot GameObject along with a character controller and colliders etc. As they pre-exist, it is not necessary to create the animations themselves.  However, it is useful to see how they are used in the overall workings of an animated character. The tutorial provides help on setting up the character and setting it in motion. However, I am clear that I will need to learn in far more depth and to gain experience in creating and animating 3D objects such as this. 

**Running and jumping**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-3.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

It is interesting that, as soon as my almost-twelve-year-old son came home from school and saw what I was doing, he was hooked! This is not entirely surprising; it _looks_ like a game, after all, even if it is not a game (yet). But it is also the magic of making things happen on a screen of some description. This became clear when I came back after a break only to find him adding colour and 'furniture' (mainly blocks and a tree stump), and attempting to amend the scripts to allow the robot to jump over, walk on, bounce off them - in other words, _interact_ with them! Perhaps this is an expression of an innate need to engage with the imagined world; to create; to interfere. I do wonder, if it had looked less like the kind of 'game' he recognises, would he have been so interested in deconstructing my creation? **This could be worth investigating.**

In any case, this led to my _getting involved_, engaging with the playfulness of my son. I found that by playing with colliders and certain GameObject settings - such as the 'slope' options - we were able to get the robot to jump over the blocks and to 'climb' onto them. From that point, adding more items and encouraging the robot to interact with them, became an imperative, something we just had to do; it was a natural progression. 

If nothing else, this demonstrates how real-life actions, engagement with the creative process and experimentation, leads to more of the same; it sparks the imagination and encourages moving in new directions, into new territories. We began to imagine a ‘parkour’ type game where points could be scored for the most imaginative way in which an obstacle is hurdled, a wall bounced off, or a platform jumped from. The unavoidable fact is, though, that whatever this becomes, even if it never gets beyond what it is now, it is already more interesting to look at and engage with than it was before that youthful and unattached mind’s attention had been captured.

**Running and jumping.. with style!**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-5.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure> 

# Camera Setup

Just adding the CameraWork component to the robot GameObject and setting it slightly above him, completely changes the nature of the 'game' experience. Suddenly, as the controller, you are much more part of the experience, feeling more involved with what is happening. It feels more natural and less detatched than 'watching' from a distance, even if you are controlling the character's fate.  

**Camera attached**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-6.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>


However, the **robot character is not easy to control**, being limited in its ability to stop, turn without running forwards, only jump in a single, slightly 'parkour' style and it can only run at a certain speed. Of course, there is much more that can be done to improve things. However, this 'demo' does indicate how much more work would need to go into creating a more usable animated character that is enjoyable to engage and to play with.


* **[Part 1]({% link _posts/GAM720/2020-02-09-building-the-multiplayer-environment-part1.markdown %})**
* **[Part 3]({% link _posts/GAM720/2020-02-12-building-the-multiplayer-environment-part3.markdown %})**