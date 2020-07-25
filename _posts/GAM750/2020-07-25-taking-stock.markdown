---
layout: post
title: Taking Stock - Sprint 1 Retrospective
date: 2020-07-25 10:00
published: true
---

# As Sprint 1 comes to a close, what have I achieved?

* I have looked at the potential of **[Unity XR plug-in framework](https://docs.unity3d.com/Manual/XR.html)** as a replacement for Oculus Integration, which, accoring to Unity, will be deprecated in a future release. For now, I have decided to continue using Oculus Integration as it is a framework I with which I have experience, is mature, well-documented, and is still being developed by Oculus with the very interesting inclusing of hand-tracking - potentially something that will be experimented with during this project.
* I have looked at the potential of **[Unity XR plug-in framework](https://docs.unity3d.com/Manual/XR.html)** as a replacement for Oculus Integration, which, accoring to Unity, will be deprecated in _"a future release"_. However - **STOP PRESS** - I have now installed the latest version of Unity - 2020.1 - in which it appears that the old XR integration **has** been deprecated. However, it also appears that Oculus Integration **has not** been replaced, but actually fits in with the new Unity framework. In fact, it appears to be very easy to integrate - I just needed to enable **XR Plug-in Management** and it appears to work seamlessly with Oculus Integration! I do not need to import any XR package, as was required when using the XR plug-in in my earlier experiments. The package manager appears to be much tidyer than it was too.

**Old XR Settings have now disappeared**
![Unity 2020.1 changes to XR Integration and Package Manager](\images\GAM750\unity-xr-deprecated-2020.jpg)
<br><br>

**New XR Plug-in Management**
![Unity 2020.1 changes to XR Integration and Package Manager](\images\GAM750\unity-xr-plugin-1.jpg)
<br><br>

**Old vs New Package Manager**
![Unity 2020.1 changes to XR Integration and Package Manager](\images\GAM750\unity-xr-plugin-2.jpg)


* I have tested several potential options for creating a multiplayer environment. This has enabled me to make an informed decision to use **[Normcore](https://normcore.io/)**. Although it is relatively new and is still in beta, it has the potential to simplify the process of syncing objects and events within multiplayer environments.
* I have created a player character/avatar that syncs accross all clients, including transforms and voice captured via the microphone.
* I have created game objects whose transforms are synced across clients.
* I have learned how to create custom components that can sync across clients, such as mesh colour.
* I have created a custom component that syncs an abstract, numerical variable value across clients.

# What do I still need to do?

* Learn how to stream data, images, video and sound from external sources into the environment where it can be displayed in realtime.

# Future research, once all this has been achieved

* How to separate incoming video streams for individual performers so as to place them discretely onto individually-designated displays within the VR environment.
* How to separate and route individual voice data from specific players within the VR environment to 
  1. other players within and sharing the VR environment  
  2. performers external to the VR environment.
* How to stream video capture from within the VR environment out to external devices. This will allow an external 'audience' to live-view the environment via, for example, Google Cardboard devices or simply on mobile device screens.

I will add more items here as I think of them...