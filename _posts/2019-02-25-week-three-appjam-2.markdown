---
layout: post
title: Week 3 - AppJam 2 - The Odd Word Out
published: true
---

### **<center><span style="color:darkblue">Odd Word Out</span></center>**
<br>
#### <center>Line up the words in your cross-hair</center>
#### <center>But only shoot if your target is stinking up the place</center>
#### <center>Only shoot if your target is the Odd Word Out!</center><br><br>

This is the embryonic idea of a more arcade-influenced version of the word-games discussed in my previous journal entry.
<br><br>
![The Odd Word Out 1](\images\the-odd-word-out-1.jpg)<br><br>
My initial idea for such a game was for the player to single out the word that is not related to any of the other words that appear on screen. The effect of the words shimmering into existence for a short while before disappearing into the ether should be mesmeric, hypnotic, rhythmic, pulsating - like light-houses. The speed could increase and the time the words appear shortened as the game progresses. As a starting point I liked the potential of this idea. <br><br>
**The mechanics** <br>
Using ideas outlined earlier surrounding the use of online Web API services for generating words and related meanings, I imagined a random word being taken as a 'seed' and used to generate multiple related words. Added to this list of _synonyms_ would be another, completely unrelated word - this would be the _target_. For the unrelated word I had hoped to use an **API service with a facility dedicated to producing random words**. Finding one that is free and available and that produces usable results proved, given the time limitations, to be not possible. A point was reached where I needed to make a decision - continue looking for such an API or continue, in the knowledge that I could use 'dummy' data for the purpose of development. Understanding how easy it could be to get caught stuck trying to solve a problem that is surmountable in the short term, I decided to move forward without the API during this phase.<br><br>
![The Odd Word Out 2](\images\the-odd-word-out-2.jpg)<br><br>
**Arcade-style word games**<br>
These same basic mechanical principles could potentially underpin numerous game ideas and strategies. Armed with this knowledge, in a fairly whimsical moment I was taken back to the now relatively simple, but hugely enjoyable, games of my youth. I found myself entertaining thoughts of thesaurus-generated aliens being shot down, eaten or knocked out by ping-pong balls. I decided this was a relatively fertile territory and the direction I should continue to explore. I realised that even if I was ultimately not able to recreate or, perhaps more accurately, plunder from such a unique and timeless classic as **Asteroids**, at least I could maybe make use of the simple ideas underpinning this game as the inspiration for something new.
<br><br>
![Word Arcade Games](\images\word-arcade-1.jpg)<br>


**The Game**<br>
Having spent around 12 hours thinking, mapping and reflecting on my ideas so far, I felt this was the point at which I should just _get on with it_! I took the _Asteroids_ idea as inspiration and, without much further planning or thinking about possible end results, I started to bash at my keyboard. First thing was to set up an environment.  I decided to use Angular for this project. I have been learning Angular for the past few months and this provided an opportunity to consolidate what I've learned thus far. I am also finding TypeScript to be an enjoyable language to work in and, as it compiles down into JavaScript, it integrates fully with the browser and the DOM, providing an immediate, light and interactive environment for a 2D game.

**Bashing out the code**<br>
Firstly, I wanted to quickly get something moving on my screen, so I found a simple JavaScript routine online that moves a div from one corner of a containing div to the opposite. I translated this into TypeScript in my Angular app and amended it to give the div the freedom to move all over the container and to bounce off walls: _the div had become a ball_. I then created another 'ball' to act as the main player in the game. This ball was not required to set off on a trajectory at a specified direction and speed, but required keyboard input in order to move, the speed increasing the longer the direction keys were pressed - this provides the ball with inertia, similar to the space-craft in _Asteroids_. 
At this point I needed more 'opponent' balls to bounce around the playing area, so I placed the particulars of the first ball into an object-class and placed this object into an array of objects. The more objects added to the array the more balls that exist on the page. Each of these balls have their own values in terms of direction of travel and speed, so they can act independently. 
<br><br>
**Ideas developing during development**<br>
The plan was always to have each object contain a unique word. Rather than this being a shoot-em-up style game, I decided that the simplest way to make this playable and fun within a relatively short space of time, would be for the player's ball to bash into the other balls and for winning or losing to be dependent on whether the balls being hit are displaying _related_ or _non-related_ words. For this to work, each ball-object would need to store its specific word as a property and collisions between these objects would need to be detected.<br>
I created a service that calls one of the thesaurus APIs I'd found.  As a seed for this API I created a list of 'dummy' random words. Ultimately, I would expect this list to be replaced by random words provided by another API, but as yet I have not found one that suits the purpose. The seed word becomes the player's own word, whilst a limited selection of synonyms from the thesaurus decorate opponent balls. Then a further selection of balls are given random words.  Collisions are detected for each ball as it moves on to its next step in its path across the screen. If a ball's coordinates coincide with the player's ball's coordinates, then a collision has been detected and the opponent ball's _hit_ property is set to true. Once all the balls that _do not_ carry words from the thesaurus have been hit then the game has been won. If all the balls that _do_ carry related words have been hit then it's _game over_.
<br><br>

<figure class="video_container">
  <video style="width:1120px;" autoplay loop>
    <source src="\media\odd-word-out.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

<br><br>

[Click here to play the game](https://stephenbanbury.com/)

Use the _arrow keys_ to navigate your player

**Summing up**<br>
Once I'd reached this point I decided to halt development - at least, for the purpose of the AppJam project. Close to **thirty-two hours** had passed since I began - approximately **twelve hours planning** followed by **twenty hours coding**. There had not been an absolute and tightly-defined product known from the start, but as the project progressed, the idea gradually developed and took shape along lines that evolved over time. Perhaps I could have spent more time planning and creating wire-frames, but I reached a point where I thought _what's the point when I know what I'm going to do?_ - I just wanted to start putting the idea into code. This approach worked on this occasion, but I realise I may need to spend more time on at the planning stage on future projects.

Ultimately the time available was plenty for what I wanted to achieve and I have a fairly clear idea of how I'd like to further develop this idea given the time. If I were to use the full available 48 hours, and beyond, I would certainly concentrate and focus on the game's **educational value** and any improvements and further development of the game's playability and aesthetic would be with this in mind: -
* find a true random word generating API
* improve and develop the game's cycle, such as progression through levels of increasing difficulty
* an interesting system of scoring and indicating progress, possibly with added features such as 'power-ups' and extended game-plays.
* give the game a its own particular aesthetic, a 'look' that helps define itself and stand out as unique, through graphic 'characters' rather than simple square divs, with the words becoming an intrinsic part of the character-graphics, rather than 'hacked' on as they currently are.
* follow the aesthetic through to an interesting-looking scoreboard and player-progress panel.
* smoother motion - possibly refactor game making use of a JavaScript library for graphics and animation, such as [p5.js](http://p5js.org/).
* add sound and music to help bring the game to life.
* make the game compatible with mobile devices and touch-screen - maybe I could refactor using a cross-platform solution using a framework such as Ioniq or NativeScript.

# There is significant potential for further development of the concept of arcade-style word games.
 
As it is, the game is quite playable and I feel satisfied that I have essentially achieved what I set out to achieve. I have also learned new skills along the way.
* I have investigated and made use of online API services
* created something playable that is intrinsically bound to the use of the API
* successfully moved away from what was becoming a vaguely 'intellectual' exercise that I felt was in danger of not being as interesting as I had hoped it would be
* made creative use of Angular - the platform I've been learning
* created some simple animation - this is new to me and is exciting to make things happen on a screen
* most of this is new territory for me and that, in itself, is exciting.

It has been a hugely enjoyable experience and one that I feel I have come out from with a much clearer idea of what is possible and what is required, not only in terms of future projects on the MA course, but towards my long-term future as a Creative App Developer.

