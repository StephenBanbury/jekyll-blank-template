---
layout: post
title: Creating The Screens 1
date: 2020-09-01 01:00
published: true
---

# The screen object

Initial prototypes were based on simplicity and guess-work. In fact they were too small and not quite the correct dimension. They also had no detail but were, instead, simple slabs.

Dimensions were later provided for the screen alone and for its frame, along with resourses including model diagrams, sketches and a SketchUp model. The latter I have not been able to import as it is created within a newer version of SketchUp than mine - but I will see if there is a way.

There is a very specific visual identity for the screen, which the director is keen to use. The physical screens have frames which are connected and hinged, allowing them to be folded and maneouvred, in order to create spaces that can morph into differ in shapes and sizes.

The screen material itself is designed for projections. However, in my case, I needed to include a video player for local video material and a canvas onto which an Agora Surface can be created. Both of these are attached to the containing screen object as children and can be switched on and off as required.

**Single screen**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\single-screen-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

**Multiple screens**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\multiple-screens-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

# Screen Formations

Formations need to be able to morph, from one formation to another. I have been considering how this should best be done: -

* **Unity physics**: in this scenario each frame would be hinged and when one is physically moved by a virtual presense in the space or other means, then the screens attached will also be affected. This seems a nice-to-have feature, but could be fraught with difficulties, particularly in the short space of time available.
* **Plotting the locations** of the screens on the ground, and then moving the points over time, dragging the screens into new positions, creating new formations. This would appear to provide a lot of control over where and how the screens move, but could be time-consuming.
* **Unity animations**: this could a relatively straighforward option. Would this be for individual screens - all 16 of them - or for a formation as a whole? This would be a major question when formulating a solution.
* **Other animation methods**: using DoTween or similar could be an interesting way forward. However, I have not used the asset yet, although I did pay for the Pro version some months back. DoTween looks a good package, but I'd need to study and experiment with it first.

# Spawning screens

I created a **class model** for screen position that holds the _Vector3_ coordinates and rotation data, in degrees, and a **service** to provide lists of position data for each screen in a formation.

This data is then read and assigned to each screen as it is instantiated into the space. Calling the method easily allows each formation to be immediately created. Should I end up using such data to move between two points (e.g. x1 => x2, y1 => y2, z1 => z2) then this will be very useful. Even if this is not the final method I use, it is very useful to hold this data, as a record, in order to recreate formations whenever I need to, whether this is during runtime or during development and editing. 

**Simple formations**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\screen-formations-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

**Example formation with associated coordinates**
![Screen Formation Image](\images\GAM750\formation-1.jpg)
![Screen Formation Image Coordinates](\images\GAM750\formation-1-coordinates.jpg)




