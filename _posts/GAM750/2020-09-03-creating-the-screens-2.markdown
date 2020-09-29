---
layout: post
title: Creating The Screens 2
date: 2020-09-03 01:00
published: true
---

# Animations

I came across an interesting-looking Unity animation asset - **[DOTween](http://dotween.demigiant.com/)** - whilst working on the ShelterBox project. In fact, so interesting it looked I purchased the **['pro' version ](http://dotween.demigiant.com/pro.php)** before even using it; I had a feeling it would come in handy in future projects even if I didn't get to use it at the time. And, sure enough, this has been the case.

DOTween has many features, but the main attration for me was the way it allows complex tweening and manipulation of animations via code and, as such, can be controlled within the codebase of the project without having to resort to the somewhat 'clunky' (in my opinion) animation creation tools available out of Unity the box. 

I have used it here in order to tween between one set of _Vector3_ and _Rotation_ data for a formation of screens and another. So it turns out my method of recording the coordinates data for each formation, as outlined in my previous post, was **the correct thing to do!**

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\screenanimations-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>


<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\screenanimations-2.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

# Creating the formations

Creating the actual formations involved much laborious moving and positioning of screens in the Unity editor, as well as some **calculating** of coordinates in order to create specific shapes. For example, the **isosceles triangle** required the three angles to be calculated depending on the lengths of the sides. As there are 16 screens, the triangle ended up having two sides comprising six screens and one side of four. To save me time, I used an **[online calculation tool](https://www.triangle-calculator.com/?what=iso)**. The Angles of the points of the triangle were therefore calculated thus:

![Isoscelese triangle calculation](\images\GAM750\calc-isoscelese-triangle.JPG)



<p float="left">
  <img style="margin: 5px" src="\images\GAM750\formation-6.JPG" width="45%" />
  <img style="margin: 5px" src="\images\GAM750\formation-5.JPG" width="45%" /> 
  <img style="margin: 5px" src="\images\GAM750\formation-4.JPG" width="45%" />
  <img style="margin: 5px" src="\images\GAM750\formation-3.JPG" width="45%" />
  <img style="margin: 5px" src="\images\GAM750\formation-2.JPG" width="45%" />
</p>