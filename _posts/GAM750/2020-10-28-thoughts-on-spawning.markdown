---
layout: post
title: To Spawn Or Not To Spawn...
date: 2020-10-28 00:00
published: true
---

I has been put to me that usually it is best practice to create all objects that appear within a scene directly in the Unity editor, rather than to _instantiate_ them at run-time.  A main reason behind this is that it allows collaboration to happen more easily: a model or texture artist, for instance, can do their work directly in the editor, changing, removing and adding objects with ease, whereas instantiated scenes would clearly hinder this process, as they could only work during run-time and would lose any work, unless it were somehow stored and then recreated in the instantiation code.  

_This is a very good point!_

In fact, not just the artist, but the developer can benefit from this approach, as it is often simpler to work visually using the Unity tools that it is to work in code or, as I have been doing, some hybrid of the two.

The temptation, as a coder, is to use code to create everything, but perhaps this instinct should be resisited. Constants, such as scenery, can be created in the editor; players, characters, objects that have 'life', can be spawned.

# How does this affect what I have done so far and what do I now need to do?

In the current context, this means some re-working. For example,  the advantage of my spawning approach is that I have the data on the objects that have been added to the scene, which is essential, for example, when animating the screens between one formation and another. I need to look at this the _other way around_. Instead of creating the screens from the stored data, I now perhaps need to gather the positional data from the physical screens and store that for future reference. 

This means a significant amount of refactoring lies ahead. Pragmatically, it may be best to approach this via a _'half-way-house'_, where the congruence between the physical models and their data is taken for granted, simply due to the fact that their physical existence is purely due to their having been created directly from this data in the first instance! The problems that will start to creep in will be due to any divergance between the stored data and the physical entities that no longer have an inseperable relationship. As such, then, I see this being a gradual process. 

# Why change at all?

Good question! If accepted to usually be best practice in the context of working in Unity, particularly with potential collaborators, then moving forward this is something I need to consider for future projects, and this is a good time to get started.


# Are my screens 'characters'?

As I have mentioned above, scenery can be built in the editor. However, objects such as players and characters that come and go can be spawned. The question that is begging is, are my screens more analogous to scenery or player-characters? As _actional objects_, they certainly do not remain static and are affected and controlled by the players. Their data and vital statistics are essential to their function and appearance over time. 

I'm going to have to think about this. I am starting to come full circle and beginning to think of these formations as prime candidates for spawning. 

Whatever the outcome in this case, the point still stands that not everything needs to be instantiated, and that only certain, very specific types of objects need the kind of fine controlling that requires a process of spawning into the environment.
