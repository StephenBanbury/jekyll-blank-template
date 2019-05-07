---
layout: post
title: Week Six - Graphics and Animation Research
published: true
---

# Outcomes from week four SMART goal
## The _sprint_

**User story**
>As an aspiring developer of game and game-like web-based apps , I would like to have the tools and know-how in order to create and animate interesting 2D graphics within a web browser.
<br>

**Task**
>Research graphics and animation software, languages, libraries and techniques - predominently 2D but taking in 3D if interesting and/or relevant.

<br>

**The process**

Firstly, as I have no firm idea of where to start, I will take a somewhat _scattershot_ approach. Below I will firstly show a brief indication - not much more than a list - of what I found during my initial research. Following this, I will delve a little further into a selection of the results from which, given I am now coming from a more informed position, I will have begun forming an idea of any potential for my purpose.
<br><br>

## Animation<br>
Whist researching browser-based animation solutions, I innevitably came across some that are more specificially oriented towards games or that are probably more suitable for attractive and interactive website design.<br>

**[anime.js](https://animejs.com/)**

![Anime JS](\images\animejs.gif)

* open source
* fast
* lightweight
<br>

**[three.js](https://threejs.org/)**

![Three JS](\images\threejs.jpg)

* 3D rendering engine
* Been around a while - well established but maybe being superceded.
<br>

**[velocity.js](http://velocityjs.org/)**

![Velocity JS](\images\velocityjs.png)

* Not the best for games
* Used in WhatsApp
<br>

**[popmotion.js](https://popmotion.io/)**

![Popmotion](\images\popmotion.png)
<br>

**[mojs](https://github.com/mojs/mojs/)**

![MoJS](\images\mojs.png)
<br> 

**[phaser](https://phaser.io/)**

![Phaser](\images\phaser.jpg)

* Game engine
* Very popular
* Good with typescript
* Looks good for 2D games especially
* Did come across some complaints about its architecture and how well-written it is
<br>

**[Greensock GSAP](https://greensock.com/)**

![Greensock GSAP](\images\greensock.png)

* Been around a long time and is very well supported
* large community
* Works well with pure JavaScript, of course, and with Vue, React and Angular. 
* The Angular angle (!) I need to investigate further.
* But.. it is perhaps a bit corporate? Logos, business website animations?
* Some of the libraries, such as Draggable, could be very useful for more simple games 
* Autism games / apps come to mind. 

**[Starwars Arcade - an example of GASP with Pixi.js](https://www.goodboydigital.com/case-study/star-wars-arcade)**

**[pixi.js](http://www.pixijs.com/)**

![Pixi JS](\images\pixijs.jpg)

* Open source
* Rendering engine
* demos on website look impressive
* above example of Pixi.js with GASP is impressive

**[p5.js](https://p5js.org/)**

![p5.js](\images\p5js.png)

* Drawing library
* Looks good for sound / animation in the browser
    * [p5.sound library reference](https://p5js.org/reference/#/libraries/p5.sound)
    * [a discussion](https://discourse.processing.org/t/based-on-what-i-want-to-do-should-i-learn-processing-or-p5-js/1425/8)
<br>

**[Some impressive browser-based animation games](http://cycleblob.com/)**

**[Making an animated sprite image in JavaScript](https://medium.com/dailyjs/how-to-build-a-simple-sprite-animation-in-javascript-b764644244aa)**

<br><br><br>

## **Game** frameworks and rendering engines
**[List of HTML5 game engines](https://html5gameengine.com/)**
<br>

**2D engines**
* [pixi.js](https://github.com/GoodBoyDigital/pixi.js)
* [GDevelop](https://gdevelop-app.com/)
* [kiwi.js](http://www.kiwijs.org)
* [Phaser](https://phaser.io/)
* [melon.js](http://melonjs.org/)
* [Crafty](http://craftyjs.com/)
<br>

**3D engines**
* [BabylonJS](https://www.babylonjs.com/)
* [Three.js](http://threejs.org/)
* [PlayCanvas](http://playcanvas.com/)
<br>

**Adobe Creative Cloud - a suite of creative tools**
[Adobe Animate CC](https://www.adobe.com/uk/products/animate.html)
<br><br><br>


## **WebVR** - this I intend to explore later on the course.

![WebVR](\images\webvr-logo-square-small.png)
<br><br><br>

# One of the most useful articles I have found: -
**[Web Animation — A comprehensive overview](https://medium.com/@evejweinberg/web-animation-everything-you-need-to-know-in-too-much-detail-91bf5d48f980)**<br>
>For more complex animations and interactions, you’ll want javascript. There are two libraries I would start with (and a thousands more out there). I recommend [greensock](https://greensock.com/) for manipulating DOM elements, and [mo.js](http://mojs.io/) for making animations from scratch in javascript.

# A great comprehensive list of the best JavaScript games engines
**[colorlib](https://colorlib.com/wp/javascript-engines-for-building-games/)**<br>
>Truly it has been a wonderful sight to watch the online gaming industry go from using Flash and Java to power their games, to using powerful 2D and 3D gaming engines that mostly are run through JavaScript and HTML5.

# Another Top 10 list of JavaScript game engines
**[jscrambler blog](https://blog.jscrambler.com/10-javascript-engines-to-develop-your-own-mobile-and-web-games/)**<br>
>JavaScript has already proved its capacity when it comes to developing top-quality games. And as you might expect from a language that counts with so many frameworks and libraries, there are tons of game engine options that can fit your programming skills and needs.


**[GreenSock 101 course](https://ihatetomatoes.net/get-greensock-101/)**
<br><br><br>

## Further research

**To greater or lesser extents, I would like to take a slightly deeper look at: -**
* CSS transformations / animations
* Canvas
* pixi.js (rendering engine)
* p5.js (graphics/drawing)
* phaser.js (game framework)
* Babylon / PlayCanvas (3D rendering)
<br>

**A potential complication** - and I am currently not sure how big a complication it may be - is that I have been working in **Angular** and would not like to deviate from this framework. As these are JavaScript libraries they should be able to integrate, but the tutorials will no doubt make use of _pure_ JavaScript. There will undoubtedly be some fildding about and further research to bring them into an Angular environment.

# **CSS**
The staple of the world wide web, the DOM, and all web design. 
I need to get to know at least its capabilities before getting to know what the various JavaScript libraries and rendering engines can provide that is different, i.e. that cannot be done with CSS, or could be done in an easier, quicker or more efficient way.<br>

I will attempt to pick up the basics of what I think I will need from CSS, and fill in any gaps as I learn the libraries, frameworks and engines. I may find that I do not need everying, so I will not set out to attempt to understand everything. Ultimately, it about getting enough information to start using it in my apps (currently I'm working on my AppJam project, The Odd Word Out).

**What can CSS do?**

Ability to create client-interactive effects.<br>
Can produce some complex effects. Best used directly for interesting visual and interactive<br>
web pages. Games etc?.. probably less so.<br>

[Animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)<br>

**Turorials**

[lynda - transitions](https://www.lynda.com/CSS-tutorials/Apply-CSS-transitions/674608/739908-4.html)<br>
Transition from initial to final state.<br>
[lynda - transition timing](https://www.lynda.com/CSS-tutorials/Manage-transition-timing/674608/739909-4.html)<br>
The _way_ the transition happens, over time.<br>
[lynda - transition steps and delays](https://www.lynda.com/CSS-tutorials/Steps-delays/674608/739910-4.html)<br>
The transition always happens _moving towards_ the state set in CSS. So different transitions can be set in initial and end states, so transition is different in one direction to when returning to original state.<br>
[lynda - asymmetric transition](https://www.lynda.com/CSS-tutorials/Create-asymmetric-transition/674608/739911-4.html)<br>
[2D Transformation styles](https://www.lynda.com/CSS-tutorials/2D-transformation-styles/674608/739913-4.html)<br>
[Combining translations](https://www.lynda.com/CSS-tutorials/Combine-transformations/674608/739914-4.html)<br>
[Matrix Transformations](https://www.lynda.com/CSS-tutorials/matrix-transformation/674608/739915-4.html) - can be used to do all these transformations.<br>
[Multiple matrix transforms](https://www.lynda.com/CSS-tutorials/Multiply-matrix-transformations/674608/739916-4.html)<br>

**Matrix transformations are used by most computer imaging programs**

[Translations in 3D space](https://www.lynda.com/CSS-tutorials/Translations-3D-space/674608/739918-4.html)<br>

This Lynda course also covers rotation and perspective in 3D.
<br>

# **PixiJS**
What is Pixi?

**_March 23rd 2019_**

[From PixiJS tutorial](https://github.com/kittykatattack/learningPixi#introduction):<br>
>Pixi is an extremely fast 2D sprite rendering engine. What does that mean? It means that it helps you to display, animate and manage interactive graphics so that it's easy for you to make games and applications using JavaScript and other HTML5 technologies. It has a sensible, uncluttered API and includes many useful features, like supporting texture atlases and providing a streamlined system for animating sprites (interactive images). It also gives you a complete scene graph so that you can create hierarchies of nested sprites (sprites inside sprites), as well as letting you attach mouse and touch events directly to sprites. And, most importantly, Pixi gets out of your way so that you can use as much or as little of it as you want to, adapt it to your personal coding style, and integrate it seamlessly with other useful frameworks...

>The strength of Pixi’s API is that it’s general-purpose: it’s not a game engine. That’s good because it gives you total expressive freedom to make anything you like, and wrap your own custom game engine around it.<br>


The tutorial suggests learning Unix. A webserver needs to be run in the root project directory and [http-server](https://github.com/nodeapps/http-server) is suggested for this purpose. Of course, I'd love to follow this option, as I'd love to follow all options ever given to me, in order to become the most knowledgable and versatile developer ever to have lived. However, I would like to pick up as much as I can in as short a time as I can. As I said earlier, I will fill in holes that need to be filled, later.

So I am going to use _Brackets_ for now. Mongoose webserver may be the next optpion to take, but just to learn and to try some coding, _Brackets_ will do. Actually, as I'm going to be working in Angular, I don't think I will need a separate webserver as importing the libraries into the Angular project and then hosting the dev project with _$ ng serve_ should do the trick. But it's _Brackets_ for now.

**_March 24th 2019_**

This wasn't a problem at all. I installed http-server: 

{% highlight cmd %}
npm install http-server -g
{% endhighlight %}

and used VSCode. Simple!

Incentally, Brackets is a very useful tool as it it does not require a server and is very immediate. VSCode is still my IDE of choice, but Brackets has found a place in my heart.

To kick start my foray into PixiJS I followed a short four-part series of videos on YouTube [CJGammon Pixi course](https://www.youtube.com/watch?v=GuY_PROTr0I) being the first. It was very useful in terms of getting started with no prior knowledge.  I've since started looking at the official documentation with a much better idea of what is involved. Sometimes, the visual 'taught', 'hold-my-hand' method is the best way to get into a new subject.  Once given a foot-hold, further subjects are much more easily tackled.

I do want to start using this in my Angular project as soon as possible. All the courses and documentation use pure JavaScrip.  However, I am going to see how easy it is to follow and learn the subject whilst simultaneously 'translating' into TypeScipt and, with possibly more difficulty, the Angular framework.

This means ensuring my Odd Word Out project is safe in source control and I'm happy to hack away in order to replace the current methods with Pixi.

Advantages of Pixi (and this could be said of other options): -
* Uses WebGL as standard and if not available will use Canvas
* Hardware acceleration
* Built-in methods and classes that make working with graphical animation accessible without having to build everything from scratch.
* Integration with Game Engines, such as Phaser, GDevelop etc.
<br><br>

**_March 27th 2019_**

# **I've been using PixiJS - what are my thoughts?**

In terms of what I think I need for my app / game development, PixiJS does not really feel _'right'_ (<span style="color:red">* but see notes below</span>). I don't feel comfortable with it as a way of achieving what I have already managed to do with 'pure' JavaScript (via TypeScript, if you can call this methodology 'pure JavaScript'). In particular, I have not found any accessible way into creating individual graphic objects that have their own unique properties, such as the word they carry, their direction of movement and their speed. I'm sure that this must be possible, but I want to find out how to do this quickly, and the available documentation does not make this information easily available.

I am considering looking at p5.js because, from what I've seen in the many youtube videos available, it may be a better fit to my current knowledge and pattern of coding more comfortably.
<br><br>

**_March 28th 2019_**

**It's amazing how much can change in a day!** Through perseverance and persistence I've found out how to 
add objects and any number of properties to a Sprite (or any kind of graphic) object. It now seems obvious - as this is a JavaScript library it makes sense that, as with JavaScript, properties can be created and attached to an object by just refering to them! In TypeScript: -

{% highlight typescript %}
let player:Sprite = new Sprite();
player.id = 1;
player.text = 'my text';
//adds properties id and text to player object and gives them values
{% endhighlight %}

**So easy!**

I've managed to transfer the methods employed in my existing code onto to the new requirements of PixiJS and a new way of working. The movement is smooth and controllable, e.g. velocity, and collisions are easy to detect. There's plenty still for me to get my teeth into and to learn, but I've satisfied myself that I have chosen a useful new way of exploring browser-based graphics and animation.
<br><br>
**The video below shows my appjam project after converting to use PixiJS.**

Two things worth mentioning: -
1. I had to turn off hardware acceleration in Chrome in order to capture the video (the software I use - _Open Broadcast Software (OBS)_ - will not work with it switched on). As Pixi makes use of hardware acceleration, the result is slower,less smooth and tends to stutter.
2. I grabbed any image I could find to use for the sprite - this would clearly be something different - possibly a balloon - as I continue to develop the game and will likely use sprite sheets for individual sprite animations.
3. I changed the gameplay so that characters wrap around the screen rather than bounce of the edges. I'm not sure which I prefer, but it could be possible to use both options for different levels as the game progresses.


<br>

<figure class="video_container">
  <video style="width:1120px;" autoplay loop>
    <source src="\media\odd-word-out-pixi.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>
<br>

# **Summary**
I've learned a lot from this sprint: -
1. **CSS transformations**: I knew little to speak of about this subject, but now I have enough of a knowledge to be feel confident I can, or at least know it is possible and, therefore, I can find out how to, make some interesting effects in order to add greater levels of interaction and interest to my apps and websites. 
2. In **PixiJS**, I have engaged with a popular JavaScript animation library / rendering engine, with good support and a good community, and have a pretty firm grounding from which to further explore and integrate animations in my future work.
3. I have researched other JavaScript animation libraries and know there are options other than PixiJS that will have their own advantages for specific uses, and **I am looking forward to further exploration of these** in due course.
4. I have become more aware of the existence of **JavaScript Game Engines** and know I can call on these if needs arise.
5. I have become aware of the exciting possiblities of the **3D graphics libraries and frameworks** which, in particular, are at the forefront of developing the possibilities of **WebVR** in the web browser. 
# These I **must** explore in due course!!



