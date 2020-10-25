---
layout: post
title: Multispace 2
date: 2020-10-24 00:00
published: true
---

# Creating multiple scenes from an orginal template

Having given the concept of mutlple spaces some thought, where each space represents a _scene_ in the multiplayer theatre environment, it became clear that I could make use of the existing infrastructure I have already put in place (see **[Creating the screens 1]({% link _posts/GAM750/2020-09-01-creating-the-screens-1.markdown %})** and **[Creating the screens 2]({% link _posts/GAM750/2020-09-03-creating-the-screens-2.markdown %})**). 

This method uses a class model for each screen formation, comprising definitions for the postition and rotation of each of the sixteen screen display panels within the respective formation. This information is then used when instantiating, or _spawning_, the formation. Animations are created by _tweening_ between the previous formation's positioning data and that of the next formation. This has, thus far, been happening in a single location, i.e. that set in each formation's respective model. 

Taking this concept and applying it to the creating of a second (or third or fourth etc.) formation, it becomes clear that the existing definitions can be used as a template, with an _offset_ applied in order to translate the positional information from the original formation to another in another place within the world space. 

This approach requires a set of definitions for the locations of each scene within the world space. If the original scene is set at _Vector3(0, 0, 0)_, then the second scene can exist at _Vector3(20, 0, 0)_, and the third at _Vector3(20, 0, 20)_ etc. 
It is then simply a case of applying this information in order to offset the original formation's positional data. The rotations must remain the same as we do not want the screens to change direction!
<br><br>

**Transversing the multispace**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\transverse-multispace-2.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>
<br><br>

**Scene position definitions within the world space**<br><br>
![GetScenePosition](\images\GAM750\GetScenePosition-1.JPG)
<br><br>

**Screen formations, showing screen positions offset by selected scene postition**<br><br>
![ScreenFormationService](\images\GAM750\ScreenFormationService-1.JPG)
<br><br>

**Scene detail model, showing how each scene comprises a scene position in world space, a screen formation definition, and references to the actual screens that have been instantiated**<br><br>
![SceneDetailModel](\images\GAM750\SceneDetailModel.JPG)
<br><br>

**Screen position model for each individual screen**<br><br>
![SceneDetailModel](\images\GAM750\ScreenFormationModel.JPG)
<br><br>


**Code behind the multispace**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\multispace-code-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>