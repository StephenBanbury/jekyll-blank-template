---
layout: post
title: Building The Multiplayer Environment
published: true
---

## Photon PUN 2 & Unity

The Photon PUN documentation, which appear to be as clear as I'd hoped, provides what looks to be a fairly straightforward [tutorial](https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/intro) towards creating a simple multiplayer enabled application. 

The API documentation can be found [here](https://doc-api.photonengine.com/en/pun/v2/index.html).

# Connections and joining rooms

The first piece of code, attached to an empty GameObject, is to connect to the Photon Cloud server and attempt to join a random room - if no room exists then one is created and that is joined. This was one of those rare magic moments, when it worked first time! Unity PlayerPrefs is used to strore the player's entered user name across states, thus maintaining it for the next time the app is started.

This Tutorial, as is usually the case with kind of thing, is not specifically aimed at the kind of work I intend to do.  Instead, it appears to use a fairly generic game pattern - I've yet to penetrate deaply enough to truly be sure as to how generic - as a vehicle for introducing the core ideas and concepts behind Photon PUN 2. I have often found in these cases that it is generally useful to continue the course, if not to its completion, then at least some way in to it - or at least until it is felt that enough core concepts have been unearthed for work to begin with the confidence that anything new and unknown can be researched as and when it is required. The balancing trick is in assessing whether this point has been reached.

Initially, I created four scenes, each representing a room in which the players can enter. I used the convention whereby the name of the room follows the number of players that have joined, and so, as a new player joins, all the players move to the corresponding room. Conversely, as a player leaves, all players move to a room with 1 less player in its title.

Use is made of the PUN callbacks (exposed through **MonoBehaviourPunCallbacks**, which extends the standard Unity MonoBehaviour class) to detect if players join or leave. 

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\pun-connect-2.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

# Building and animating the player character

The tutorial has a useful introduction to [building and animating the player character(s)](https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/player-prefab). This is not PUN-specific so comes as an unexpected but welcome addition, as character animation is something that I will need to look into.

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\robot-animation-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

# DeltaTime
>Read as much as you can on the topic and what you'll find when searching the web for this. After you understood the concept, you'll be able to make the most out of many Unity features when it comes to animation and consistent control of values over time



