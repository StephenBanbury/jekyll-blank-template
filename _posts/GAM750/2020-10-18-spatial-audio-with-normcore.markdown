---
layout: post
title: Spatial Audio With Normcore
date: 2020-10-18 01:00
published: true
---

# Out-of-the-box: audio appears to be 2D!
During the first realtime testing with the project's expert stakeholders, i.e. the director and technical director, I was eager to see if audio between players is 3D / spatialised, i.e. can be used to sense distance and direction. Unfortunately, it appeared to be very much 2D and unspatialised; there was no volume roll-off - no matter how near or far apart we were from each other, the volume of the voice was constant.

This is a real shame. 

I am now looking into possible solutions for this. I am hoping that is will be as straightforward as a simple setting somewhere, or a case of adding a 3D sound source to the VR player. 

# Testing: two headsets are better than one
Question: How do you test this with only a single headset? 
Answer: With great difficulty!

Testing multiplayer environments is not the only reason I bought a new Oculus Quest 2, but it is the main one. Or, at least, it's a good excuse!

Not only can I now experience multiplayer applicaitons with family and friends, but I can also test my own developments. Not to mention that the latest model is much faster and has a much better display, at a cheaper price point. Seemed to make sense to me!

Setting up is a bit of a problem, though, because Facebook now insist that you use a FB account! It is not even possible just to use your old Oculus account - it now must be linked to a FB account, even if you continue to use it only on your current headset. Bad, bad Facebook! This means that, in order to play multiplayer, **I need to sign in on different accounts**. For this reason, I set up a second FB account attached to a second user on my Android phone. I will have to log into each, separately, and use each account to log into each headset, separately. What a faff!

Back to the spacial audio issue...

# First port of call: Normcore Discord server

[01-05-2019] 
> if you're using the built-in spatializer, then you can fix easily by changing this line in AudioOutput.cs:
> 
    data[sOut] = !_mute ? audioData[sIn] : 0.0f;

> just change that to this:
>
    data[sOut] *= !_mute ? audioData[sIn] : 0.0f;

> the input value to that OnAudioFilterRead() is set up to be 1.0 * whatever attenuation Unity has added to the AudioSource including volume

----

[01-09-2020]
> I think in V1 I had disabled the built-in spatialization

----

[02-09-2020]
> Question: How do I make the player voice 3D? (e.g. how do i make them louder the closer you are to them, and quieter when you are further away? - by default you can hear people constantly)

[02-09-2020]
> take a look at the audio source on your avatar (make sure the "spatial" slider is set to "3d") and you can muck with the falloff values on there if you want to customize it.
Unity defaults to 2D, and the falloff range is basically "100% volume up to 5 meters, still audible 100 meters away" or something like that, so it's definitely tuned for larger spaces.

[02-09-2020]
> if you add an audio source RealtimeAvatarVoice will detect it and use it instead of creating one
you can use SetActive, but you'll also need to make a custom RealtimeComponent in order to synchronize the active state. Normcore doesn't synchronize that part for you

[04-09-2020]  
> I followed your advice to add an audio source to the RealtimeAvatarVoice gameobject in order to allow the spatial blend of the player's voice to be 3d, however its still behaving like its 2D - any idea on what could be wrong?
general/04-09-2020

[04-09-2020] 

> if you’re on V1, try making this change:
[if you’re on V1, try making this change:
https://discord.com/channels/393839515074297858/393841777091543052/573241867185946680
](if you’re on V1, try making this change:
https://discord.com/channels/393839515074297858/393841777091543052/573241867185946680)


