---
layout: post
title: Week 3 - AppJam 1 - Three Little Words
published: false
---

### **<center><span style="color:darkblue">Three Little Words</span></center>** 
<br>
**Three words**: selected randomly using VNA (_**v**erb, **n**oun, **a**djective_) cards form the basis of the App Jam activity - an intensive period of development and reflective practice.<br><br>
**48 hours**: the time allocated for this activity. Although it has been suggested that we should try to use the full 48 hours, it is also recognised that we may not be able to find such an amount - after all, it is time which has to exist alongside the usual course study, reading, learning, journal-writing and, of course, everyday life. In my case, the latter is particularly time-consuming in itself, being as it involves a working life and a young and demanding family. At this stage I find I really have little idea of how much time 48 hours is - at least in the sense of finding despersed pockets here and there in which to allocate time both for pure development and for reflection. This is uncharted territory for me. This being the case, I have decided not to try to plan too much in advance but to move forward for short periods before pausing and evaluating what I have done. Hopefully, these moments of reflection will provide the basis and knowledge from which I can plan my next steps.<br><br>


### _<center><span style="color:darkblue">Guide : Opponent : Restricted</span></center>_ 

As well as deciding to use at least one of these three words to help define the nature of my app, I also started looking at them, not so much for their individual or collective literal meanings, as for the fact that they, as do all words, have the ability to be transformed and reinterpretted. This can be via, for example, context, order or re-assignment of grammatical useage such as between, for instance, verb, noun, adjective etc.
<br>

**<center>Verb</center>** | **<center>Noun</center>** | **<center>Adjective</center>** | **<center>Adverb</center>**
_<center>Guide</center>_ | _<center>Guide</center>_ | _<center>Guidable</center>_ | _<center>Guidingly</center>_
_<center>Oppose</center>_ | _<center>Opponent</center>_ | _<center>Opposing</center>_ | _<center>Opposingly</center>_
_<center>Restrict</center>_ | _<center>Restrictiveness</center>_ | _<center>Restricted</center>_ | _<center>Restrictedly</center>_<br>

**Using our words in different sentences transformed by their grammatical useage: -**<br>
>She restricts but guides her opponent<br>
>The guide opposes being restricted<br>
>She is restricted by her opposition<br>
>His opponent is guided by her restrictiveness<br>
>They offer her guidance but in a restricted way<br>
>His opposition to the guide was being restricted<br>
>She is being restricted by the guide<br>
<br>

**I looked into the concepts that come to mind when considering how meanings can be transformed**
<br><br>
![app-jam-mind-map-1](\images\app-jam-mind-map-1.jpg)<br><br>
.. a path that led me on to thoughts of understanding and mis-understanding, interpretation, translation, encoding and decoding, encrypting and decrypting, symbols, signs, perception and the idea of the actual **medium itself** being the message (_Marshall McLuhan, 1967_). 

<br>
**The thesaurus**<br>
The thesaurus is used, usually, to find similar (synonym) or opposite (antonym) words. However, a synonym can sometimes stretch the original meaning so far from its origin that the connection breaks. This can be interesting to explore in itself - the point where meaning is lost in translation and new meanings - or a lack of - unfold. The image below shows the result of playing with a thesaurus in attempting to create sentences similar in meaning to the original but using completely different words. Each word is replaced by a synonym, then the new word replaced with a synonym of its own, and so on. The most synificant disconnects have been highlighted in red. The most stark disconnections are where there are multiple meanings for a word, particularly where each of those meanings are relatively sparce in terms of their own synonyms. For example, 'brown' is very specific - it has few alternatives - but 'fawn' is one of them. However, there are more meanings than those associated with 'brown' only. We can therefore easily get words, such as 'baby-buck' which have nothing whatsover to do with the colour brown and ends up providing potential new sentences with totally new meanings.
<br><br>
![app-jam-mind-map-2](\images\app-jam-mind-map-2.jpg)<br><br>
<br>
A startling result of this break-down can be seen in the difference betwen the first and last sentences: -
>The quick brown fox jumps over the lazy dog
<br>
>The bountiful angelic phony promenades facing the baffled assistant

<br>
I began to imagine this effect being played out in some kind of animated graphical representation similar to a **fruit machine** or a **tombola**, where sentences are constructed from the results of thesaurus lookups for each of their composite words.<br><br>
Another possible direction is to replace words with images - a full change of media adding further to the abstraction. This could be an interesting way to move forward. A major challenge is finding a convincing way that these ideas can be converted into an interesting and usable game. I decided to let the ideas develop as I played with the materials and mechanisms I found during research and experimentation - it seems there must be a rich source of possibilities that lie in this direction, waiting to be discovered and manipulated as they are uncovered.
<br><br>
I began a search for an online thesaurus with API endpoints I can access for the purpose of abstracting words.
I found a number of thesaurus APIs - some are fully open and free whilst others either require an account to be created in order to access an authentication key or will only allow paid access. Most ask for a creditation and a link on any web application or site produced using their service.  I signed up to the free services where appropriate.:<br><br>
[ProgrammableWeb](https://www.programmableweb.com) - API directory<br>
[Big Huge Thesaurus](https://words.bighugelabs.com/api.php) - thesaurus<br>
[Datamuse API](https://www.datamuse.com/api/) - word-finding query engine for developers<br>
[STANDS4 Web Services](https://www.phrases.net/phrases_api.php) - phrases, lyrics, quotes etc.<br>
[WordsAPI](https://www.wordsapi.com/) - some services free<br>
[Opinionated Quotes](https://opinionated-quotes-api.gigalixirapp.com/) - quotations API<br>
[pixabay](https://pixabay.com/api/docs/) - picture gallery API<br>
<br>
**A problem**<br>
After a little while exploring what these kind of APIs could offer, I was presented with a problem: none of these, except maybe one, can provide a random selection of words, phrases, quotations, or any other form of language output that can be used to drive a game such as those I had in mind. The one API I could find that will generate anything random is [Opinionated Quotes](https://opinionated-quotes-api.gigalixirapp.com/), which produces random quotations that are generally so obscure and specialised within a particular subject, interest or market, that any use of these would would expect users to have an extensive, wide and varied knowledge of some fairly 'niche' subjects.<br><br>
**How to proceed..**<br>
So I find myself with a delema: -
1. how to produce interesting and useful words, in the sense of their not being too prescriptive in their raw form and useful in this current context. 
2. considering the formats these words appear to be available to me, how am I going to use them?
Hopefully solutions will come as I work through these issues step by step.
Perhaps I can produce some quotes and phrases through some kind of AI, using something like Amazon Alexa to generate texts. Or perhaps I could look into **web scraping / crawling** and find useable text by actually going and looking for it. Scaping is actually something that appeals to me - I hope to come back to at some point in the future. Would I need to develop a database of my own or can I access an existing one using an intelligent search facility?<br>
**Here's one:** [Common Crawl](https://commoncrawl.org/) - _"We build and maintain an open repository of web crawl data that can be accessed and analyzed by anyone."_.  
<br>

**A possible solution?**<br>
[Datamuse API](https://www.datamuse.com/api/) provides varied ways of searching for words - e.g. 'sounds like', 'means like', 'spelled like', 'related word', 'starts with letter', 'contains letter' etc. This could be very useful in a game led more by the players themselves, rather than the by the capabilities of API itself. The random aspect problem will still be there to be solved, but perhaps it is something that can be added at a later date, but for now this should not detract from moving forward and allowing a general idea of an app or game from developing.
<br><br>

**Formulating ideas for games**<br>
..how could I make use of such an API?<br>

**A suite of simple games for bored car passengers**<br>
_Looking for a reasonable and achievable use of the time I have left on the App Jam._<br>
Perhaps I could develop a suite of word games or activities of the type that families use to pass the time on long car journeys.<br>
There are a number of possibilities that Datamuse API can be used for, if it is used creatively. I could also make use of a thesaurus API if required. <br>
At this point, I have potentially around forty hours left - if I set myself the goal of producing concepts for four games in quick succession, giving myself two hours on each one, I will have around thirty-two hours left in which to put together wire-frame representations of the concepts. If I again give myself two hours for each game, then I will have approximately twenty-eight hours in which to make a stab at coding them. I may find that time slips here and there, or that I have given myself too much to do. I will allow for a small amount of lee-way, but will force myself to cut off short rather than eat into the next phase.<br><br>
**I Spy** : using 'sounds like', 'begins with' etc.<br>
**Chinese Whispers** - developed from the concept outlined earlier, where meanings change through small incremental 'misunderstandings' introduced via the thesaurus.<br>
**Guess the word** : present player with text with certain words replaced with synonyms or antonyms - the player must guess the real word.<br><br>

## <span style="color:darkblue">**Any Word** - a word-guessing game</span>
..similar to **_'I Spy..'_**<br><br>
**_"Think of a word, any word"_**<br><br>
![Any Word 1](\images\any-word-1.jpg)<br><br>
The idea is that players (showing two here, but could be more) present their **opponent** with a series of **guiding** questions about a word they have in mind. Datamuse API provides facilities for producing answers that could fit these kinds of questions - 'sounds like', 'begins with', 'related to' etc. <br>
The opponent will make a guess and, if wrong will be presented with the next clue. <br><br>
![Any Word 2](\images\any-word-2.jpg)

* The game will be between two or more players: **Opponent**<br>
* The game will be constrained by the capabilities of the API: **Restricted**<br>
* The first player leads the second player towards the correct word: **Guide**<br><br>


**One small step forwards, but the treasure in sight is starting to lose its lustre**<br>
Having reviewed this process after making a start on mapping an idea for one of the possible games, I have decided it would be appear to be too much to try to build a suite of games at this stage. I believe that, for now, simply showing the _possibility_ of creating a suite is enough. I have found that it hasn't taken long to confirm the suspicion that it would be all too easy to underestimate the amount of work involved in realising such an ambitious target.  At least, it is ambitious for me. With more experience of this kind of creative development activity and, of course, the app jam concept itself, I would hope to be 
 1. able to work faster
 2. have a better idea of what I will need to do next
 3. know how to manage my own expectations

The main reason for trying to take on several small apps in a suite, stems from my concern that the single idea I've spent most of the time on is actually _not as interesting as I'd like or thought it would be_. Maybe it is neither _exciting_ enough as a game nor _interesting_ enough as an intellectual excercise. However, it is difficult to know, at this stage, if this will ultimately turn out to be true. 

Perhaps, if the relatively simple idea behind the games are embellished by clever game-play that graphically represents the progress players are making in an interesting, creative and aesthetically-pleasing way, then the game will be bestowed with more appeal, appearing to be more unique and able to stand on their own. 
<br><br>
**Making the game-play more interesting**<br>
A selection of ideas for making a fairly stayed intellectual game into something that may have a bit more of a buzz about it..<br>
* Build a tower
* Fill a grid
* Knock down a wall
* Cross a river / road / lake / island
* Climb a mountain
* Destroy
* Be destroyed

At this stage I feel I am moving away from my initial ideas and towards something that could be considered challenging in a more 'gamic', rather than purely intellectual, sense. For the player, a sense of progress and achievement can maybe be gained not just from the ability to solve puzzles, but from being able to do so in a more challenging environment, that is more immersive, interactive and ultimately... **fun!**

