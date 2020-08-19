---
layout: post
title: Multiplayer Synchronisation
date: 2020-08-07 02:00
published: true
---

# **Using Normcore for two main objectives**:

# 1. Syncronising transforms

Normcore includes pre-built scripts that directly synchronise GameObject transforms between clients. Very simpley put, once an object has been designated to have a _'realtime transform'_, it will automatically be kept in sync. 

The same goes for players' avatars, which allows them to interact within the shared 'room'.

Objects can be 'owned' by a player, allowing them to manipulate their position or other transforms. If an object is designated to have the ability to transfer ownership, then more players within the room can also interact with it. 

Although this is extremely simplified, it does highlight how these concepts allow rapid development of the multiplayer environment.

# 2. Syncronising abstract values


Translating values when values change and events are raised. In this case, selecting a video and assigning it to a display screen.



