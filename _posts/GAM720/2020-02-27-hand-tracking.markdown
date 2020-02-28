---
layout: post
title: Hand Tracking
published: true
---

# Why hand-tracking?

Controllers in Virtual Reality are at once extremely well-designed, precision pieces of equipment that make interaction between human beings and virtual worlds a more than reasonably seemless and intuitive experience. However, these controllers, no matter how well-designed, insist on a certain amount of experience with this kind of thing. Not everyone posesses a reasonably extensive experience honing their video-gaming expertise whilst immersing themselves in worlds that can best, or perhaps, only be adequately accessed and fully appreciated through devices that allow them to be experienced on their own terms. In this sense they actually form a barrier - one that can be enjoyable and aid increased immersiveness for those searching for such experiences though videogames - but one that could potentially be off-putting to those who are inexperienced in such media. Simply teaching those who have never experienced virtual reality - easily representing the majorty of the potential audience at a non-enthusiast exhibition - would take time and effot, some of which will have been wasted when the a potential user decides that this is not for them after all. 

Hand tracking, then, could be a useful 'leveler', where almost anyone can relate their physical experience as human beings to actions interpreted and imagined within a virtual scenario.  In the case of ShelterBox, it may be that a reduction of the time needed to teach matters as mundane as using the controllers will allow more time to experience the media and to think about issues of great importance.

# Setting up and using Oculus Quest hand tracking

This is a new feature for the Quest as of December 2019. It is steadily improving as the weeks roll by.
However, it's new-ness and the continual roll-out of updates brings its own problems: - 

* Tutorials can become out of date very quickly and gradually become less relevant or realistic to follow
* Your own set up can get behind the curve and changes you need to incorporate in order to include the latest features can mean at least some headache.
* There is little community of knowledge to approach for answers, as everyone has similary questions 

I began by following [this tutorial](https://www.youtube.com/watch?v=vSia7t_WlbQ) by Valem (a Belgian guy called Quentin, I believe) and there were a few issues getting going, due to the video being a whole two-months old. In Quest years that's way past the innocence of childhood and is now hitting puberty. Updating the Unity Oculus Integration package fixed some problems, and thinking around other problems fixed those. There's not much point in putting too much detail here because it will likely have become irrelevant in a matter of months, or in Quest Years, before we hit late teens.

Hand tracking was, when he made the video, only possible in Android mode and did not include the ability to work using Oculus Link, i.e. running the Quest from a PC connected via a (fast, quality) USB cable. A later update - v13 of the Oculus firmware - in February, has now made this possible.  

I went straight for the Link promise, with unexpected results!

**Nighmare hands! .. oh dear, that wasn't supposed to happen!**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\hand-tracking-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

Actually, not totally unexpected, at least in terms of it not going righ at first. But the actual look of the hands is very.. ahem.. interesting!

**Hands correctly configured**
<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\hand-tracking-2.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

The hands, once configured correctly, do respond fairly well to realtime movements - there is a small amount of latency, but they do tend to 'wobble', or twitch a little, particularly at the ends of the fingers. Presumably this is due to inaccuracies when attempting to keep track. It feels like a slightly weak WiFi or telephone signal and there is the sense that, if only the signal were better then the results would be much tighter and more solid and, therefore, more realistic. 

The fact, though, that this is achieved with just a headset, making use of no extra hardware or specialist software aside from Oculus' own, provided for free (to those who have already paid for the equipment, of course), is impressive at this time. I would like to see if specialist hardware/software solutions, such as [ultraleap](https://www.ultraleap.com/) become available for the Quest, particularly when not in Oculus Link mode. The main advantage of the Quest is that it can function perfectly well untethered - in fact, that is its primary focus and, as much as Oculus Link has provided another dimension, almost making the tethered-only Rift redundant, for me, the ability to be fully operational in any location and without any reliance on a computer with a reasonably high-end graphics card, is very important. But at the current time the in-built cameras on the Quest appear to do a reasonable job and the advantages - portability, simplicity and price - are not to be underestimated. 

I will be studying next how to grab and throw using hand-tracking. But it also concerns me how movement will be achieved with no joystick controls - just bare hands - and I will also be looking into this issue..



