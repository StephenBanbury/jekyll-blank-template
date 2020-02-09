---
layout: post
title: Building The Multiplayer Environement
published: true
---

## Photon PUN2 & Unity

The Photon PUN documentation, which appear to be as clear as I'd hoped, provides what looks to be a fairly straightforward [tutorial](https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/intro) towards creating a simple multiplayer enabled application. 

The API documentation can be found [here](https://doc-api.photonengine.com/en/pun/v2/index.html).

The first piece of code, attached to an empty GameObject, is to connect to the Photon Cloud server and attempt to join a random room - if no room exists then one is created and that is joined. This was one of those rare magic moments, when it worked first time! Unity PlayerPrefs is used to strore the player's entered user name across states, thus maintaining it for the next time the app is started.

<figure class="video_container">
  <video style="width:1080px;" autoplay loop>
    <source src="\media\pun-connect-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>




