---
layout: post
title: Multiplayer research
published: true
---

My wish to create events within a shared virtual space will require some method of inviting two or more individuals to participate within a single environment. There appear to be a number of options that I will need to research in order to better understand the potential differences, similarities, advantages and disadvantages.

# Past musings

Having never made a multiplayer game I'm starting from a very low base. However, more than one of my ideas for a creative app during ideation for GAM730 - the co-creative project - included multiplayer settings. At the time, without undertaking any serious research, I considered using a Firebase **[Firestore](https://firebase.google.com/docs/firestore)** database as a central hub, to which multiple clients could connect. This appeared to offer the most important aspect of interconnectivity - a full-duplex connection that immediately pushes any changes made to the database, by any connected client app, out to all other connected client apps. Beyond this, I did not do much further investigating. As I am about to embark on a full scale research activity I will find out just how naive this thinking was. Or not, as the case may be. I'm sure it's not going to be as simple as this, but the fundamentals of WebSocket-style connectivity and a central database must, surely, be a major part! I shall find out.

# In no particular order: options recommended, returned as search results, and other discoveries along the way

* **Unity Networking: _[Depricated](https://support.unity3d.com/hc/en-us/articles/360001252086-UNet-Deprecation-FAQ)_**<br><br>
  >UNet, Unity’s legacy multiplayer solution, does not meet the needs of many multiplayer game creators. To reach the performance, scale, and security goals of Unity creators, we’ve reached the difficult decision that completely new technology is required, including lightweight and fast networking, and a dedicated game server model.

* **[Photon PUN 2](https://www.photonengine.com/en-US/PUN)**
  
  >Photon is a real-time multiplayer game development framework that is fast, lean and flexible. Photon consists of a server and multiple client SDKs for major platforms - [Photon API documentation](https://doc-api.photonengine.com/en/pun/v2/)

  * The Photon Unity Networking library (PUN) immediately stands out due to its integration with Unity.
  * It supports peer-to-peer networking, rather than all messages needing to transmit via the host. This means PUN is pretty fast, accoring to **[raywenderlich.com](https://www.raywenderlich.com/1142814-introduction-to-multiplayer-games-with-unity-and-photon)**, when compared with, say, Unity's own networking solution.
  ![Unity Transport Layer API](\images\unity-photon-api-difference.png)
  * PUN provides 20 Concurrent Users (CCU) for free, along with 8000 monthly activities and 500 messages per room, plus an option of $95 for three years, including 100 CCUs and 40K monthly activities. This is certainly interesting for small indie developers, who are certain to be on a budget.
  * It appears that tutorials and documentation are a strong point and there are a decent number of tutorial videos available on YouTube.
  <br><br>

  This immediately looks interesting as I do not want to spend much of the 9 weeks development time available (three sprints of 3 weeks each) setting up complex structures of my own, such as multiplayer server, database and websocket connections. The fact that this is free for low-level development, and reasonably-priced should I need to step up a level, also adds appeal. 


# So what is **Photon Bolt** and how does it differ to Photon PUN 2?

* **[Bolt](https://www.photonengine.com/bolt)**

They are game networking middleware. 
A comparison is provided **[here](https://doc.photonengine.com/en-us/pun/v2/reference/pun-vs-bolt)**

Basic summary of difference: **Host Client (Bolt) Vs. Dedicated Server (PUN)**

* With **PUN**, if the Master Client (i.e. special client that acts in a similar way to a dedicated host) quits, another actor -if available- will become the new Master Client. And so on, until there are no more clients.
* With **Bolt**, on the other hand, the server is "static"; the "client" that starts up the game and choose to become the server, will stay as the server. If the host client (server) quits, none of the other clients will become a server (and all of them will be disconnected, of course.)

Bolt appears to be take more control away from the developer, which can be a time-saver. I'm leaning towards the greater control provided by PUN as I would like to gain a greater depth of understanding of the processes involved. In any case, I like to have more control over what I am doing!

Automatic compression is a bonus for Bolt, whereas the PUN developer may have to implement it themself. However, PUN sends data from client to other peers through the relay by default (without passing through the master-client). Conversely, Bolt _always_ has to pass through the hosting machine, thus adding latency.

* **[Google Agones](https://cloud.google.com/blog/products/gcp/introducing-agones-open-source-multiplayer-dedicated-game-server-hosting-built-on-kubernetes)**

Open-source, multiplayer, dedicated game-server hosting built on Kubernetes. This is something I'd like to find out more about. In particular the fact that it uses Kubernetes, another technology I've had in my sights for some time, and it is Google, which is certainly not one of the smaller companies. The fact that it is still relatively early days perhaps makes it less appealing when I'm looking for something to get set up and running quickly and is supported by a large base of users and documentation. However, I'm sure it, or its successors, will have a big future in the field.

* **[Nakama](https://heroiclabs.com/docs/)**

Nakama is an open-source scalable server for building social and realtime apps and games.
Looks very interesting but maybe a bit heavyweight for my needs.

# Conclusion

I haven't spent an exhaustive amount of time researching theses options and I'm sure there are even more out there. The task is made more difficult because I am researching a subject I know little to nothing about and, therefore, I find myself not completely certain if the diffent products I am reading about exist for the same purpose or if the apparent subtle differences are, in fact, major ones. 

Google Agones and Nakama look interesting, but I am uncertain if how they would be put into use. If I had more time then perhaps I'd look further into their potential, but for now, I feel they will demand too much of my time when I really want to get on with building something.

Photon PUN 2 and Photon Bolt are both interesting and, in comparison with the offerings from Google and Nakama, I find the quantity and clarity of documentation, tutorials and general discussion surrounding them to to be helpful to my understanding of their purpose. Pricing structure for both is the same. However, despite the apparent greater simplicity of Bolt over PUN, the latter is more appealing due to the greater control and potential for learning and acquiring a greater depth of understanding through its use. 

Therefore, I shall begin delving deeper into the potential of **Photon PUN 2** as a multiplayer server solution for my project.



* **VRTK**<br>

with PUN?

**[Good news!](https://forums.oculusvr.com/developer/discussion/76611/does-oculus-quest-support-photon-unity-networking)**

>I am researching about possibilities to make multi user experiences for the Quest and have been wondering if Photon would help?
> - yes

**[PlayoVR, a VRTK-PUN-Voice Demo](https://github.com/quintesse/PlayoVR)**
