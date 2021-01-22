---
layout: post
title: Persisting Multiplayer State
date: 2020-11-12 00:00
published: true
---

# When players join late
When I first put together the multiplayer environment, I imagined that every player would begin at the same time. It did not then occur to me that some players may join later, or leave and then rejoin. Therefore, it seemed reasonable to simply ensure that each change made to the environment by an individual player, such as assigning a video to a screen, could be immediately passed to all other clients and, because all clients had been there from the start, each will experience the same results, from the same chain of successive actions, as every other client in the multiplayer environment.

However, what if a player joins late? They will have missed the series of actions that has led to what the other players see in their shared environment. Only the latest action will be stored and 'known' about by the multiplayer engine, as only the last action is held in the Normcore datastore. The player will, therefore, only see the latest video to be added.

# A standard solution
I considered how this could be corrected. The 'usual' way to deal with this would be for the joining player to query one of the existing players - without their knowledge, of course - in order to find out what screens have so far been affected. I can see that this approach would could result in certain problems and is not necessarily an ideal solution: which player would you query? Have they all been there since the start? If not, you'd need to find out which had been. Either that, or they'd all have to be updated with the full set of changes, which would be load on resources. Where would this data be stored - locally?

# RealtimeArray

Normcore has a special model type that holds an **[array of realtime models](https://normcore.io/documentation/reference/serialization-realtimearray.html)**. I'd been using realtime models so far to keep data syncronised between clients. Each model can be seen as a class model comrising a number of primative data types. The _RealtimeArray_ holds an array of such models. This is **exactly** what I have been looking for!

Normcore describes the RealtimeArray thus: -

>It is designed to be a sequential list of models that can be modified at runtime.<br>
Modifying the array sends the minimal amount of information necessary for other clients to replicate the change. The whole collection is not sent every time.

The Normcore tutorial **[Creating a multiplayer drawing app](https://normcore.io/documentation/xr-guides/creating-a-multiplayer-drawing-app.html)** demonstrates the use of a RealtimeArray. It does not use it in exactly the same way, so there is a real need to fully understand the concept in order to use it in your own project, but once it had 'clicked', it made absolute sense. 

Now, if a player joins in late, they are updated with all the screen video changes that have been made from the start.
<br>

<figure class="video_container">
  <video style="width:720px;" autoplay loop muted>
    <source src="\media\GAM750\persist-all-screens-for-connecting-player.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

There is an issue with a delay while the joining player's environment is updated - this is not helped by the fact that, for each screen, a video has begin streaming from a remote location accessed from its URL. If the videoes were local this would be a lot quicker. 

# RealtimeSet

Normcore has another special model type called a **[RealtimeSet](https://normcore.io/documentation/reference/serialization-realtimeset.html)**. This may speed up things - I will attempt to replace the RealtimeArray with the RealtimeSet in due course.

>RealtimeSet is a special model type that can be used in your own custom models. It represents an unordered collection of models. Internally this is used for things like keeping track of all RealtimeViews in the scene. If order is not important, this collection is the recommended collection to use for storing collections of models.<br>
Adding or removing items sends the minimal amount of information to the server in order to perform the update on all clients. The whole collection is not sent every time.


I have not yet managed to test this with live video streams from performers' webcams, so there may be some work to be done here. But the theory is the same, so it should work with, hopefully, the minimum of tweaking.

