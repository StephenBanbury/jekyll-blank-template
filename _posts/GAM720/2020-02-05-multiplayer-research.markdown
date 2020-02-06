---
layout: post
title: Multiplayer research
published: false
---

My wish to create events within a shared virtual space will require some method of inviting two or more individuals to participate within a single environment. There appear to be a number of options that I will need to research in order to better understand the potential differences, similarities, advantages and disadvantages.

# Past musings

Having never made a multiplayer game I'm starting from a very low base. However, more than one of my ideas for a creative app during ideation for GAM730 - the co-creative project - included multiplayer settings. At the time, without undertaking any serious research, I considered using a Firebase **[Firestore](https://firebase.google.com/docs/firestore)** database as a central hub, to which multiple clients could connect. This appeared to offer the most important aspect of interconnectivity - a full-duplex connection that immediately pushes any changes made to the database, by any connected client app, out to all other connected client apps. Beyond this, I did not do much further investigating. As I am about to embark on a full scale research activity I will find out just how naive this thinking was. Or not, as the case may be. I'm sure it's not going to be as simple as this, but the fundamentals of WebSocket-style connectivity and a central database must, surely, be a major part! I shall find out.

# In no particular order: options recommended, returned as search results, and other discoveries along the way

* **Photon**
  
  >Photon is a real-time multiplayer game development framework that is fast, lean and flexible. Photon consists of a server and multiple client SDKs for major platforms - [Photon API documentation](https://doc-api.photonengine.com/en/pun/v2/)

  * The Photon Unity Networking library (PUN) immediately stands out due to its integration with Unity.
  * It supports peer-to-peer networking, rather than all messages needing to transmit via the host. This means PUN is pretty fast, accoring to **[raywenderlich.com](https://www.raywenderlich.com/1142814-introduction-to-multiplayer-games-with-unity-and-photon)**, when compared with, say, Unity's own networking solution - at least, accoring to this account. I am loath to take an opinion and go with it without checking out its validity, and I hope to do this later. But for now, with limited time, I think I'll take this well-respected (apparently) view on the matter and move on.
  * PUN provides 20 Concurrent Users (CCU) for free, along with 8000 monthly activities and 500 messages per room, plus an option of $95 for three years, including 100 CCUs and 40K monthly activities. This is certainly interesting for small indie developers, who are certain to be on a budget.
  * It appears that tutorials and documentation are a strong point and there are a decent number of tutorial videos available on YouTube.
  * **[PUN website](https://www.photonengine.com/en-US/PUN)**.
  <br><br>

  This immediately looks interesting as I do not want to spend much of the 9 weeks development time available (three sprints of 3 weeks each) setting up complex structures of my own, such as multiplayer server, database and websocket connections. The fact that this is free for low-level development, and reasonably-priced should I need to step up a level, also adds appeal. 


  The **[raywenderlich.com](https://www.raywenderlich.com/1142814-introduction-to-multiplayer-games-with-unity-and-photon)** tutorial is an interesting first read. However, what I do not yet know, is how it works with VR and, in particular, **avatars**. Social VR will be an upcoming topic as I do further research.

* **Onine tutorial: [VR Networking Part 1: How to Setup Multiplayer VR with Oculus and Unity](https://www.youtube.com/watch?v=yRvfLLTkIXM)** <br>
  This does not appear to be something worth ignoring. 

* **NetworkManager**<br>
  **[GameDevAcademy](https://gamedevacademy.org/how-to-create-a-multiplayer-game-in-unity/)** is an online tutorial site I have come across from time to time when looking for tutorials on various subjects related to building apps in Unity. Like most things associated with Unity, the site is explicitly game-oriented. However, this does not detract from using Unity for purposes that are not necessarily wholy devoted to games. This tutorial involves the use of the _NetworkManager_, which I know nothing about, but appears to be something that may be useful during development, such as attaching and passing objects and actions via, what apears to be, a service that manages interactions over a network.

* **VRTK**<br>

with PUN?

Good news!<br>
https://forums.oculusvr.com/developer/discussion/76611/does-oculus-quest-support-photon-unity-networking
>I am researching about possibilities to make multi user experiences for the Quest and have been wondering if Photon would help?
> - yes

**PlayoVR, a VRTK-PUN-Voice Demo**
https://github.com/quintesse/PlayoVR





