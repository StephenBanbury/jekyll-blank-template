---
layout: post
title: Building The Multiplayer Environment | Part 2
published: true
---

# Building and animating a player character

The tutorial has a useful introduction to [building and animating the player character(s)](https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/player-prefab). This is not network-specific so comes as an unexpected but welcome addition, as character animation is something that I will need to look into sooner or later.

The robot prefab is provided for demo/experimental purposes as part of the Photon PUN 2 asset download, as are the animations required to get him moving (running, swinging arms etc.). These need attaching to the robot GameObject along with a character controller and the usual collision detector etc. Although it is not necessary to create the animations as they pre-exist, it is useful to see how they are used in the overall workings of an animated character. The tutorial provides help on setting up the character and setting it in motion. However, I am clear that I will need to learn in far more depth and to gain experience in creating and animating 3D objects such as this. 

**Running and jumping**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-3.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

It is interesting that, as soon as my almost-twelve-year-old son came in from school and saw what I was doing, he was hooked! It _looks_ like a game, after all, even if it isn't a game (yet) so it's not entirely surprising. But it is also the magic of making things happen on a screen of some description. This became clear when I came back after a break only to find him adding colour and 'furniture' (mainly blocks and a tree stump), and attempting to amend the scripts to allow the robot to jump over, walk on, bounce off them - in other words, _interact_ with them! Perhaps this is an expression of an inate need to engage with the imagined world; to create; to interfere. I do wonder, if it had looked less like the kind of 'game' he recognises, would he have been so interested in deconstructing my creation? **This could be worth investigating.**

In any case, this led to my _getting involved_, engaging with the playfulness my son. I found that by playing with colliders and certain GameObject settings - such as the 'slope' options - we were able to get the robot to jump over the blocks and to 'climb' onto them. From that point, adding more items and encouraging the robot to interact with them, became an imperative, something we just had to do; it was a natural progression. 

If nothing else, this demonstrates how real life actions, engagement with the creative process and experimentation, leads to more of the same; it sparks the imagination and encourages moving in new directions, into new territories. We began to imagine a 'parkour' type game where points could be scored for the most imaginative way in which an obstacle is hurdled, a wall bounced off, or a platform jumped from.

**Running and jumping.. with style!**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-5.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

However, the **robot character is not easy to control**, being limited in its ability to stop, turn without running forwards, only jump in a single, slightly 'parkour' style and it can only run at a certain speed. Of course, there is much more that can be done to improve things. However, this 'demo' does indicate how much more work would need to go into creating a more usable animated character that is enjoyable to engage and to play with. 