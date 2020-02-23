---
layout: post
title: Unity And Graphics
published: true
---

# Lighting and Rendering

3D object shading results from the intensity, direction and colour of the light falling on it.

**Types of lighting**

* **Realtime lighting**
  In Unity - directional, spot and point. Update every frame and are interactive with moving objects. Do not bounce.
* **Baked  lighmaps**
  More complex, static. Lighting effects are written to textures overlaid on top of the scene geometry.
  Realtime lights can be overlaid **additively** on top of lightmaps.
* **Precomputed realtime global illumination**
  Offers us a technique for updating complex scene lighting interactively. Shifts some of the lengthy number-crunching from being a realtime process to one which is precomputed. An example is a time of day system, following sun position throughout the day.

Choices of type of light to use is not only dependent on the effects required, but on expense in terms of performance as a result of available processing power of target platform.


# Creating a space with SketchUp

Sketchup is a great tool for building 3D architectural spaces. I have been using an old version that was installed on my laptop for a few years and have found it fun to play with and useful for testing architectural designs. But one of the best things about it is that it was free....  '**_was_**' free.

It's now not so simple. When I first came across SketchUp it was part of Google's output and didn't cost a penny - and I was amazed! It is a well thought-out piece of software and, at the time, it really seemed incredible that something so well-designed and rivalled expensive commercial products could be available to the unwashed masses for nothing.

Since then, it appears to have been offloaded by Google and taken on by a company named Trimble (the history of SketchUp is summerised **[here](https://techcrunch.com/2012/04/26/sketchup-google-first-divestment/)**), with more recent versions covered by a subscription-style payment system - see the **[SketchUp](https://www.sketchup.com/)** site for details. However, it is possible to still download earlier versions - v8 from 2010 is a stand-alone desktop version that is totally free, and the 2017 iteration is free for non-commercial use. These older versions of SketchUp **[can be found here](https://designerhacks.com/get-the-google-sketchup-free-download/)**

SketchUp files can be easily brought into Unity. I created a pretty close rendition of the ground floor of my house and am working on being able to walk around it in VR. This stems from the idea of trying to create an environment that is familiar, comfortable, relaxing, following my train of thought on autism and education (annunciated throughout this course and this blog). I find that SketchUp provides a way to create architectural renditions of real and imagined spaces much more naturally than using the graphical tools provided within Unity, including ProBuilder and the standard Unity tools. The fact that it is simply a case of dragging the exported models directly into Unity is very useful, and the older free versions of SketchUp are absolutely fine for this purpose.

**The model in SketchUp**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\sketchup-pentre-street1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>


**The model in Unity**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\unity-pentre-street1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>
