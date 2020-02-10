---
layout: post
title: Building The Multiplayer Environment
published: true
---

## Photon PUN2 & Unity

The Photon PUN documentation, which appear to be as clear as I'd hoped, provides what looks to be a fairly straightforward [tutorial](https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/intro) towards creating a simple multiplayer enabled application. 

The API documentation can be found [here](https://doc-api.photonengine.com/en/pun/v2/index.html).

The first piece of code, attached to an empty GameObject, is to connect to the Photon Cloud server and attempt to join a random room - if no room exists then one is created and that is joined. This was one of those rare magic moments, when it worked first time! Unity PlayerPrefs is used to strore the player's entered user name across states, thus maintaining it for the next time the app is started.

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\pun-connect-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

This Tutorial, as is usually the case with kind of thing, is not specifically aimed at the kind of work I intend to do.  Instead,it uses a simple generic game pattern as a vehicle for introducing the core ideas and concepts behind PUN. Sometimes, I have found, it is useful to continue the course to, if not its completion, then at least some way in, until it is felt that enough core concepts have been unearthed for work to begin with the confidence that anything new that is needed can be researched as and when it is required. The balance is to be found in assessing whether this point has been reached.






