---
layout: post
title: Multispace 1
date: 2020-10-23 00:00
published: true
---

![Lightbulb](\images\GAM750\lightbulb.jpg)

# Thinking about multiple spaces (or multiple universes)

I've just had an interesting thought, as a respone to the problem of creating multiple _'spaces'_, which players can move between, at times that will be decided later.

If an _'environment'_ can be spawned as an object, and accessed through a set of methods and properties etc., then this will greatly ease the way in which a player can be 'dropped' into the space and interect with the objects that are present within it.

In a way, this is similar to creating multiple _scenes_ in Unity, except that these exist as entities within the same single scene.  In this form, therefore, they can exploit an outward facing _interface_ in order to interact with a Master Game Controller-type object, that controls the manner of who, what, why, and where a player can exist and function, but only within the specific space that it exists.

# Nice theory, what about the actualities?

* Negative: Could ge difficult at this stage of development, having already put much infrastructure into place.
* Positive: It is actually fairly early in development terms given a longer view on the project as a whole and its potential as we move forward

It would be a task that would include creating an interface for the space, in order to access multiple other interfaces, i.e. per method an property that is part of that space.

# But... no!

This idea would not work - I think - because the VR experience is seen from a **first person** perspective, and all code is run in a similar manner. That is, each individual instance of Unity, running in each headset, will access its own set of game objects and, on each object, a set of components. That individual is **not** controlling from heaven, but from their own person... on the ground.  The _'God'_ concept suggested above, i.e. where control is exerted down on the multispace and controlling eacn individual multiplace, could work as part of a controller interface for the use of **Stage Managers** and similar roles. But this is looking too complex for this purpose and within the available time frame.

Therefore, I will maintain this post as a reminder of a possible way to think of this Potential model in the future.
