---
layout: post
title: Week 3 - AppJam 2 - The Odd Word Out
published: false
---

### **<center><span style="color:darkblue">Odd Word Out</span></center>**
<br>
#### <center>Line up the words in your cross-hair</center>
#### <center>But only shoot if your target is stinking up the place</center>
#### <center>Only shoot if your target is the Odd Word Out!</center><br><br>

This is the embionic idea of a more arcade-influenced version of the word-games discussed in my previous journal entry.
<br><br>
![The Odd Word Out 1](\images\the-odd-word-out-1.jpg)<br><br>
My initial idea for such a game was for the player to single out the word that is not related to any of the other words that appear on screen. The effect of the words shimmering into existence for a short while before disappearing into the ether should be mesmeric, hypnotic, rhythmic, pulsating - like light-houses. The speed could increase and the time the words appear shortened as the game progresses. As a starting point I liked the potential of this idea. <br><br>
**The mechanics** <br>
Using ideas outlined earlier surrounding the use of online Web API services for generating words and related meanings, I imagined a random word being taken as a 'seed' and used to generate multiple related words. Added to this list of _synonyms_ would be another, completely unrelated word - this would be the _target_. For the unrelated word I had hoped to use an **API service with a facility dedicated to producing random words**. Finding one that is free and available and that produces usable results proved, given the time limitations, to be not possible. A point was reached where I needed to make a decision - continue looking for such an API or continue, in the knowledge that I could use 'dummy' data for the purpose of development. Understanding how easy it could be to get caught stuck trying to solve a problem that is summountable in the short term, I decided to move forward without the API during this phase.<br><br>
![The Odd Word Out 2](\images\the-odd-word-out-2.jpg)<br><br>
**Arcade-style word games**<br>
These same basic mechanical principles could potentially underpin numerous game ideas and strategies. Armed with this knowledge, in a fairly whimsical moment I was taken back to the now relatively simple, but hugely enjoyable, games of my youth. I found myself entertaining thoughts of thesaurus-generated aliens being shot down, eaten or knocked out by ping-pong balls. I decided this was a relatively fertile territory and the direction I should continue to explore. I realised that even if I was ultimately not able to recreate or, perhaps more accurately, plunder from such a unique and timeless classic as **Asteroids**, at least I could maybe make use of the simple ideas underpinning this game as the inspiration for something new.
<br><br>
![Word Arcade Games](\images\word-arcade-1.jpg)<br>


**The game** - need to work on this:-<br>
Ended up with a game that uses thesaurus via a web API, random word as seed, returns related words, mixes with unrelated words. YOu need to knock out those that are related (could be other way around) to win.
Inertia and movement around screen is inspired by Asteroids. There's also a bit of Ping Pong in there.
Could refine and change game-play. 
Education possibilities. Take into classroom - English lessons. Also could have legs in maths, geography etc. 
Successful in moving away from the 'intellectual' excercise that was a bit boring.

asteroids - moving off screen and back on other side.  bouncing off each other.

**Using the 48 hours**<br>
I had no idea at the start how long 48 hours actually is - or more accurately, how much time it would _feel like_ during the progression of the project. Although 48 sets of 60 minutes is clearly measureable, in terms of dev-time I was not completely sure where I should expect myself to be at particular points, or how I would feel in terms of my own progress. I can at least partly explain this as due to total unfamiliarity with app-jamming. Although day-jobs have seen me working as part of a development team, the AppJam has provided a whole new experience and many variables that were unfamiliar; this took me outside my comfort zone. I found myself working _as an individual_ on an unfamilar type of application (i.e. 'gamic', graphically-interactive and animation-heavy) within an unfamiliar development environment (Angular), using an unfamiliar language (Typescript). My past experience working on browser-fronted applications also belies the fact that I have not always been fully confident as a programmer; I have not had any formal training to speak of and have been predominantly learning my trade on the job. Whilst this has, in many respects, provided me with a solid grounding, it certainly does not induce a great sense of confidence that _what one does know_ is what one _needs to know_, or that any gaps that exist in ones knowledge are actually not significant enough to worry about.
<br><br>
So, I made a start thinking about the topic, mapping ideas in a fairly immediate and sketchy way, and continually assessed what I found myself doing and the thoughts and ideas I had. I started with very little in the way of an initial plan, but I responded to my developing ideas as they arose and from there I planned my next immediate move. This did allow me to be fairly **agile** in my approach; I did not, at least for very long, find myself following a path I felt I may regret. That is not to suggest I did not think about outcomes - this would have been unavoidable and, in any case, imagining where this may all lead drives the process by providing a purpose for it - but I did not allow myself to become fixated on a goal.
<br><br>
This approach worked for me in this project. However, feel that it will be necessary to develop my planning process to such an extent that there will be times when I need to be more specific in setting myself realistic and attainable goals. SMART objectives provide a framework for this. And Agile practice allows for reflection and for responding to outcomes of reflection.  This, to me means that you can set out a structured approach which gives you the framework to work towards your goal, but does not let this become too prescriptive and prohibitive by encouraging continual re-evaluation of the process as it progresses.
Actually, I think this is what I did to a great extent without it being fully formalised:<br> 
<br> SMART <br>
S - "I will create an interesting word-based game that is engaging and forces players to think about relationships between words through their meanings. I will do this by creating an Angular app and making use of one or more publicly-avaiable RESTful APIs such as a thesaurus. "
M - "I will research such APIs and find at least one that is able to provide on-demand a list of synonyms for any given word."
A - "The word API will be free, available, easy to access and provide at least enough results for development purposes"
R - "The kind of result returned by the API will lend itself to the generation of more words or the sort that word games can make use of"
T - "I will use a maximum of 48 hours to create a working and playable proof-of-concept or slice of the app"
<br><br>
<figure class="video_container">
  <video controls autoplay poster="\images\game-image.png">
    <source src="\media\odd-word-out.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
<br><br>
It's been fascinating to look back at the AppJam as a whole and at what has been achieved. From being unsure about how it would progress and what the outcome would be, to having a working product and being able to quantify the time and understand hows and whys etc. To see that goals have been achieved, and how they were achieved, along with where this can be built upon in the context of what has been learned about reflective and deliberate practice, has been remarkable for a 5 week period.<br>
The initial expectation of stress, and subsequent difficulties faced, have actually allowed me to gain a huge amount of confidence in the light of the actual outcomes when looking at how problems were overcome and, as they say, it will be alright on the night!
<br><br>




----
10-12 hours drawing thinking it through, writing and drawing ideas, and mapping out ideas. after 12 hours i decided I had enough to start coding. From there is was one step at a time towards something along the lines of my earlier contemplations. No absolute finished and tightly-defined product known from the start, but the idea gradually developed along lines I'd been considering, as I progressed.
Ultimately the time available was plenty for what I wanted to do. 
Each problem dealt with one at a time - one bounding ball. dummy data. then more bouncing balls, each as object, collisions. Add in use of the API.

[from around 36 mins] "really cool. I really like it" "take into classroom"
[see from about 39 mins]
Enjoyable experience.
Positive experience. Got a finished product in place. Looked at difference APIs along the way. 
[41 mins] 48 hours not that long. Thought it may not be long enough, but it was actually plenty. Thought I should probably spend more time planning, wire-framing etc But thought whats the point when I know what I'm going to do?
Lucky to come up with something do-able. Was this within my comfort zone and is this a good or bad thing? Should I push myself more or is this necessary? 

----
How did my experience of the AppJam relate to what I've understood and learned about Reflective Practice? 
How did my experience of the AppJam relate to what I've understood and learned about Deliberate Practice? 
How did what I've understood about these concepts get implemented or inform my practice?
What have I learned from this?

----
SMART


