---
layout: post
title: Week 1 - The Creative Piece
published: false
---

### Master Jammer

"*As long as we have each other we will never run out of problems*"

The line seems to resonate with something I have some experience with, i.e. music. This phrase could easily have been written about music itself, which can be easily seen as the presentation and attempted resolution of a series of problems. Apart from some very determined attempts in the realm of the avant-garde to detach musical production from its human-centred origins, much of what drives this production is our social nature and our determination to move forward with new ideas and to formulate responses to what has come before.

**_I began to think of how this process may be formalised into actions that could be crystallised within the medium of an app._** <br>

**Musical collaboration and how it (sometimes) works**<br>
I focused on the idea of multiple musicians creating musical ideas that pose questions that demand responses from their peers.  Looking at how musicians in a band often write songs together, whether this is via a relatively loose process of ‘jamming’ or by sitting down and meticulously working through and developing ideas, I began to see it as essentially a process whereby **_possible musical solutions are developed as a response to being confronted by a series of musical problems_**.  In this case, the chosen, ‘successful’ solution, is the one that wins through on consensus.  It is the one that draws the most admiration from those participating. Essentially, it is a form of democracy.<br>

**Not just a jam on a telephone line**<br>
I started by trying to find a formal solution to the problem of musicians, potentially dispersed across great distances, coming together in order to make music collaboratively. Rather than simply providing an open channel on the internet and providing a facility for musicians to jam their ideas across what would, in essence, be a high-quality telephone line, to an extent I wanted to deconstruct and formalise the **_actual processes of producing collaborative music_**, to bake them into something that is an **_interesting and unique activity in its own right_**.

**A game of musical collaboration**<br>
As the idea developed, I began to see how this process could be structured along workflow lines similar in some respects to a game.  The graphic below provides an attempt at mapping out one way of achieving this. I am sure that there are many ways and directions this concept could be developed. However, I decided to adhere to one possible avenue and see where it leads:-

* The game could be initialised by agreeing, at the outset, the constraints of a recognisable song structure. For example, _ABABCBD_ – or _verse, chorus, verse, chorus, middle eight, chorus, outro_. Then additional formal structures could also be agreed upon, such as measure and tempo, say _4/4 time at 120bpm_. These need not be set in stone and could potentially be amended during the game (see the graphic outline below). Drum beats could be provided as an option, along with a backing track or a chord progression, thus providing over-arching music constraints, or a restrictive 'template'. 

* The musicians – or ‘players’ - would decide who is to kick-start the process and provide the first phrase, theme or ‘riff’.  Alternatively, the app itself could kick start proceedings with an internally-generated or pre-recorded theme.

* Each player would then have the opportunity to play their response to that theme. Once all players have submitted their responses, everyone will vote on their favourite. Players would be prevented from voting for their own. The winning phrase would then be appended to the track and the others put into a ‘theme pot’.

* Points would be accumulated when a player's idea wins the vote.  The build-up of points would allow successful players to replace phrases or themes with their preferred options, or even to suggest amendments to the arrangement itself.

* The game would end when the agreed arrangement put forward at the start (and potentially amended during the game) has been completed. The winner will be the player who has had the biggest influence on the resulting song/track/masterpiece and, as a consequence, will have accumulated the most points.

![jam-master-map](\images\jam-master-map.jpg)<br><br>

**Musicality at a premium?**<br>
A significant challenge would be to make the app responsive in a way that is acceptable to musicians. If the game is to be close to being jam-like in its ambitions (without necessarily being an actual jam) then a live feel must be maintained with a fast-paced and relatively immediate 'question-response' flow.  It would be possible to adopt a more studious approach, where musicians work through their ideas in a more considered and controlled manner, but this would be quite a departure from the original concept where a maintained pace and immediacy would enhance the game with an increased sense of jeopordy and, consequently, fun. 

**Audio streaming, virtual instruments or MIDI?**<br>
Game-play is one thing - the medium is quite another.  I envisaged this as being a live play-along / play-together concept using live audio streaming via a microphone. However, it could be that virtual instruments, or even MIDI, be used instead of real instruments.  In this scenario, players would select their chosen instrument and a graphical interface would facilitate live playing.  This would likely be a piano-style keyboard but there is potential to experiment with different and unique methods of converting musical gestures into musical reality. The technology required for each of these options would be very different and each has its own appeals, advantages and shortcomings.

**Technical issues**<br>
Live streaming over the internet is inherently compromised by the inevitability of time-lag, or latency. This would clearly be a problem when streaming live audio. However, it may be possible to avoid most, if not all, such problems if the game-play is such that no actual live streaming is used. For example, players would not necessary need to play in real-time with other players. Instead, it may be that they would each play along with the recorded arrangement as it exists _thus far_, adding their own part to submit for peer voting. If it is not possible to totally avoid playing together live, then it seems that the **best latency avoidance (i.e. ping time) currently achieved averages around 40ms**, which may be perfectly serviceable in the context of this app.    

**Addressing challenges and obstaces**<br>
Aside from the above-outlined issues surrounding the physical limitations of the available technology - prodeminantly internet speed - how could this app be brought into being? This is clearly something that presents a wide set of problems and requires considerable thought and planning, backed up by a good knowledge of not only the technologies that need to be brought into play but of how they can be made to work together, with each playing their own necessary part in the attainment of a single goal. In terms of technological know-how and experience, for some time my strength has been in database and middle-to-front-end web development. Due to a desire to work more on the client-side and an interest in the user-interface, I have recently been making inroads in this direction.<br><br>
Creating an app such as this, from initial ideas and concept, through planning, prototyping and building, to deployment/hosting and marketing, will inevitably require a significant grasp of most, if not all, of the full stack of technologies. Once the prototyping phase is well underway I would expect to have a fairly comprehensive idea of what technologies and knowledge will be required and at which point a programme of research and self-learning can be put into place. At this stage I can anticipate certain areas I'd need to start to explore: for example, working with sound is something I've not done up to this point, in any form, as is streaming and web-socket technology. I have also begun to explore cloud technologies, such as those offered by AWS and Firebase, which I would expect to play a large part.<br><br>
So it's fair to say there are plenty of areas that would need to be explored and questions asked to find suitable solutions. However, I believe I have enough knowledge to know where to look for advice and answers. Such a project is one that I would commence with the certain knowledge that it will be an interesting, albeit steep, learning curve.

**What's already available on the market?**<br>
There are a number of website / app-based options facilitating musicians playing live over an internet connection. There tends to be an issue with latency / real-time lag that has not genuinely been overcome, although various efforts have been made.  Generally, though, they current offerings appear to be similar in terms of scope and ambition, offering from one or all of a selection of live jamming, online recording, social interaction & affirmation, collaboration and cloud-based sharing. 
My research did not uncover anything similar to this concept in terms of work-flow or a creation-collaboration game.

Examples are:-

* **[eJamming](http://www.ejamming.com)**<br>
Jamming over the internet.  A  simple concept that seems to work, although the demo on YouTube, to my ears, suffers slightly from latency (lag), albeit small.

* **[JamKazam](https://www.jamkazam.com)**<br>
Another jamming tool, but appears to be a hardware rather than software solution - the website does not make it very clear how this works. It appears that the idea is that musicians play along to backing tracks.

* **[Jammr](https://jammr.net)**<br>
Another jamming tool - currently in beta. Looks simple and straightforward and claims zero latency. I have not been able to test the claim of achieving zero latency, but I have doubts as to whether this is currently possible, particularly as no rivals appear to make such a claim.

* **[Avid Cloud Collaboration for Pro Tools](https://www.avid.com/pro-tools/cloud-collaboration)**<br>
Remote recording using the Avid Pro Tools platform

* **[Jamulus](http://llcon.sourceforge.net/)**<br>
Open source. Requires 200 kbps for both upstream and downstream. 40ms average latency.

* **[Soundtrap](https://www.soundtrap.com)**<br>
Cloud-based onine music and podcast recording 

* **[pibox](https://music.pibox.com)**<br>
Mix reviewing, communication, file sharing, and cloud storage

* **[vampr](http://www.vampr.me)**<br>
Mobile: Android & iOS
<br><br>

**Further possibilities**<br>
The interactive nature of an online music collaboration or jamming concept is fascinatingly open to the potential of enhancement and the development of ideas beyond connecting and interacting in a purely audio environment. I would be interested in exploring the possibilities of connecting visually and immersively, into areas of **virtual and augmented reality**. The potential for musicians to immerse themselves in a virtual environment in which they could play alongside each other could be extremely exciting. Facial recognition and 'super-imposition' technologies could potentially allow musicians to experience **playing alongside anyone, or anything, in a place of their own choosing**, including with 'celebrities' or even fictitious cartoon creations of their own making or purchased from an online library of characters.
