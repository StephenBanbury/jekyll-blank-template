---
layout: post
title: C# TCP/UDP Client-Server Tutorial
published: true
---

[Tom Weiland C# Networking Tutorials](https://www.youtube.com/playlist?list=PLXkn83W0QkfnqsK8I0RAz5AbUxfg3bOQ5)

This has been a very interesting tutorial. The objective is to build a console app server which connects clients and allows mutliplayer interaction. 

Following the tutorial and coding along are not necessarily easy bedfellows, because it is quite a complex set up. My approach is to follow what I can whilst coding and to later work out what I do not fully understand. 

By the end of the first five installments I have build a server, which allows clients to connect, spawning 'player' characters, following their movements so they can be viewed by other connected clients, and then disconnecting when a client closes down or the server closes down.

After this point I feel I really need to know how to pass data across the socket connection in order to inform other clients, via the server in this case, that something has changed in one of the client's environments. It seems I need to spawn every object that is included in any kind of interaction. This could potentially  involve lots of spawning, and then lots of data for each type of interaction, being passed across the network and then interpreted by the server before being diseminated to each client. At least, that how I believe it will require setting up, before having undertaking the course installments beyond simply moving a player character around the (so far unlimited) space.

The question here is, do I need to continue exploring the console server option, in which case, do I need to use a phyics library like [BepuPhysics](https://www.youtube.com/redirect?event=video_description&v=qkjr_rv4AIQ&redir_token=QUFFLUhqbEpGMUgxUFpzNW4yLXJUaDVGaTFXai0zRHZMUXxBQ3Jtc0ttYWNEM2VQTHlCQWk1c1E5dXhBaUZHQVp1OTFOOTVTX0tJa1lkek45Sk9vYWJhWU1OeHZfd0Y1Y0VwYm1Jb2l3dnNSeGY2SUhPSm9MS0xqM2FJaXdLemdEeVJvNmtTZXpSU1A0Y3ViWXJpbmpuTlhlcw%3D%3D&q=https%3A%2F%2Fgithub.com%2Fbepu%2Fbepuphysics2), with the alternative being to move the server code into Unity and use its in-build physics, or have I found a pathway this is actually unnecessarily complex? There is a **lot** to do - I'll need to add server-side collisions and work out how to make actions that happen on the client also happen elsewhere.  

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\c#-networking-tcp-udp-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

Instead, **can I find a simpler solution?**

Tom suggests that the reason for this setup is partly to prevent cheating. But what I am doing does not attract cheats ;). Would an alterantive such as Mirror be more appropriate? Mirror at least allows direct client-client communication once the connection has been created via the server.

Or Photon PUN 2? I found this, which sees to suggest that built-in solutions could work: [Sync Rigidbodies Over Network Using PUN 2](https://sharpcoderblog.com/blog/sync-rigidbodies-over-network-using-pun-2).

**Oh.. my.. God! Why hast Thou forsaken me?!!!!**

Both these scenarios mean that I will be bypassing a full inward transfer of networking knowledge and plumping for a relatively easy/soft/lightweight/lazy approach. I would like to fully 'get it'. But I have time and resource limitations. Perhaps it would be best, as is often the case it seems, to go for the simple option to get it up and running and then get to know the detail and complexity later? I've spent the best part of three days (i.e. evenings not spent with the family) on this tutorial... Grrrrrr!

## Normcore

I've now just come across **[Normcore]({% link _posts/GAM750/2020-07-13-normcore.markdown %})**. This looks to be yet another option...
