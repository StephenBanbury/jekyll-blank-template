---
layout: post
title: Week Three - Suspension Of Disbelief
published: true
---

# Create an Interactive Novel

**Suggestion**

>Create an interactive novel using Ren'Py, loosely based on the game creation activity from Week 2. There must be at least three interactive moments within the novel.<br>
In line with the previous activity, these decision points might be:<br>

>* Choosing which character will save the day.<br>
* Deciding how the character uses your app to save the day.<br>
* Selecting an action to execute in battle.<br>
* Ending the game, by choosing what the character will do once they have overcome the challenge, for example, do they go back to their normal life or choose to continue using their power for good or evil?<br>
  
>This activity is designed to encourage you to think outside the box and be creative with how you communicate a concept. There are no boundaries or constraints, apart from the minimum number of interactive moments in the novel. There are also no rights, wrongs or silly ideas. Do whatever feels right in regards to your main concept.

# [Ren'Py](https://www.renpy.org/)

![ren'py](\images\ren-py-main.png)

It seems to be a simple way to produce interactive text (see [Cybertext](http://www.autzones.com/din6000/textes/semaine09/Aarseth(1997).pdf)) which requires the reader/player to make choices along the way, causing the narrative to fork and head in directions that are the result of the decision that have been made. Its multi-platform nature and portability makes it particulary interesting due to the possibility of creating simple demos that are easily made available. Ren'Py scripts are simple text files that follow a simple syntax. 

# [Fungus](https://assetstore.unity.com/packages/templates/systems/fungus-34184)

![fungus](\images\fungus-main.png)

A free asset for Unity, Fungus describes itself as being _great for making Visual Novel, Interactive Fiction, RPG, Point & Click & eLearning games_.
It looks like an interesting option and, because it uses the Unity IDE, workflow and Asset Store, it could be very useful as I  increasingly make use of Unity for my projects. I believe it will also be relatively straight forward to turn the work done using Fungus into a 'full' Unity-based project. 

I am looking forward to trying out Fungus, but for this exercise I will be using Ren'Py, for it's relatively simple workflow, small file size and ability to easily port to multiple devices.

## [Dog Walker Simulator](/2020/02/04/dog-walker-simulator.html#take2)
My narrative will be based on my updated story idea which can be seen [here](/2020/02/04/dog-walker-simulator.html#take2)

**Interactive moments could be: -**
1. The dogs have broken freen from Crystal's grasp and are heading in different directions. What should be her response?
2. Which dog, or dogs, to go after first?
3. What to do when she or a dog is facing imminent danger?
4. What to do when she has collected all the dogs she is able to?

Trying to outline interactive moments in such a linear fashion is not as simple as it first appears to be, as the very nature of interactive, _[ergodic literature](https://www.articleworld.org/index.php/Ergodic_literature)_ is non-linear. For instance, point 3 may not even come to pass depending on decisions made at points 1 or 2. Therefore, the suggestions above cannot be seen as the definitive set of choices available.  Perhaps it would be better to draw up a more complex network of possibiliies. I have a feeling the alternative, of simply making a start creating the narrative and seeing where it leads, could lead to huge confusion!

![interactive-sketch1](\images\interactive-novel-sketch1.jpg)

Points: -

* Finding images is going to be difficult - will have to make them myself to do a proper job.
* Python - discovering Python through Ren'Py. The use of variables became necessary. Looking at the documentaion indicates that the whole Python vocabulary will be important.
* Vastly reduced the number of possible options by reducing number of dogs from 5 to 3 then to 2 - potential first branches reduced and therefore number of possible outcomes etc.



I began by creating a sketch, on paper, of a vague possible plan of an interactive narrative. At this stage it started to become clear how complex a web this could become given even what appeared at first to be be a reasonable number of points of choice and potential forking onto difference paths - I found it difficult to use this plan verbatim, at least in large part due to this very fact. It made me realise just how linear programming itself can be. The complexities in both providing and following instructions that involve a large number of divergent strands do not seem to sit easily within such a format. It's a little like trying to describe a three dimensional oject in two dimensions. Or, perhaps it is clearer how difficult this can be when you consider how hard it is to imagine a four dimensional world when viewed from our own perspective as fully paid up and assimilated members of one that is simply three dimensional. 

Nevertheless, branching is possible but fraught with difficulties avoiding spaghetti and repetition. I used variables to help, for instance, differenciating when revisiting a certain scenario that could have been approached from a number of possible situations, for example, rescuing Trixie after Rusty had been reunited with Crystal, or the same scene, i.e. rescuing Trixie, after Rusty had been taken away by the dog warden. Variables can also be used for maintaining states - I used one for keeping track of energy levels.

Overall, the complexities of building this interactive novel meant it was more time-intensive than I had imagined it would be - although this would clearly improve with experience. I also found that I had little time to spend searching for good quality and suitable assets, such as character and background images. To do this properly one would really have to make their own, but of course, this is a skill in itself. As it was, I picked images very quickly with little consideration for aethetic quality or cohesive design - doing so would have been unnecessary with regard to the limited intentions of the exercise.

I considered creating my own cartoon-like images, but quickly realised it would take a very long time to do so. I got as far as a single outline sketch, but to turn this into a set of usable png files (which they would need to be in order to have transparent backgrounds) would be a project in its own right!

![trixie sketch](\images\trixie-dog-sketch.jpg)

However, I did use a music track that I created myself - [**Movement (soundcloud)**](https://soundcloud.com/stephen-banbury/movement) - although clearly this was not created specifically for this project. Building a usable library of assets would make creating such an artefact much simpler and far quicker, as well as avoiding potential issues surrounding permissions and copyright. But as this would consume a huge amount of time it is certain that, at least, certain assets will always need to be acquired from suitable resources. The better quality assets are, of course, generally not free.

I do find it interesting that, awful though my selection of images are, they are still more engaging than none at all. After all, a sequential selection of visual images, even if the quality is questionable, make telling a story more immediate than textual or verbal forms alone. There is also a large body of research looking at the use of music in film and TV, as a [source of emotional impact](https://rhythmcoglab.coursepress.yale.edu/wp-content/uploads/sites/5/2014/10/Music-as-a-Source-of-Emotion-In-Film.pdf) and aiding the [setting of a 'tone'](https://books.google.co.uk/books?hl=en&lr=&id=YjZN-44Z8AcC&oi=fnd&pg=PP11&dq=film+music&ots=0uDqu6CF7c&sig=LlmWuuKRq5v0hVDJSNLD9h1U48g#v=onepage&q=film%20music&f=false).

Ren'Py, and other applications with similar aims, such as Fungus, certainly appear to be fairly popular - judging by the number of hits when searching the internet - suggesting they have a number of potential uses. As well as testing ideas for story-oriented or game-like apps, I can see the opportunity for creating interactive presentations that could be very useful for pitching or promotion. It is predominantly for this reason that I am glad to have engaged with it.

The video here demonstrates a number of different possible storylines, each dependent on the player's choices.

**Dog walker simulator**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\dog-walker-simulator.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

As a potential companion, or demonstration, of a pitch, this could be an interesting medium. A story / narrative can help explain, familiarise, a concept that otherwise relies on a the dryness of a verbal description.


