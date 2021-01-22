---
layout: post
title: Preparing for deployement 
date: 2020-12-07 00:00
published: true
---

Last minute changes, fixed etc.

Controller app:
* 'base 10' video selection buttons
* teleport every player to final scene - mutliplayer wire-up

Final scene:
* 360 degree video, 
* skybox, 
* teleport to new spawn point some distance away, 
* remove floor, 
* move overhead camera with players.

Problem with sound from screen videos - not noticed before as no sound included on videos.

An annoying problem as there appears to have been a number of changes over the years regarding how to set up audio on video clips. Eventually, a forum thread led to the answer, which is specific for clips playing from URL sources

https://forum.unity.com/threads/video-player-is-not-playing-audio.486924/

>Audio settings seem to work differently when playing from a clip and from a URL. For playing from a URL, in 2018.1.2f1, the correct sequence to set up the player is this. First, set up the player; player must be stopped for this, and not been Prepare()d yet.

    // We want to play from a URL.
    // Set the source mode FIRST, before changing audio settings;
    // as setting the source mode will reset those.
    videoPlayer.source = VideoSource.Url;
    
    // Set mode to Audio Source.
    videoPlayer.audioOutputMode = VideoAudioOutputMode.AudioSource;
    
    // We want to control one audio track with the video player
    videoPlayer.controlledAudioTrackCount = 1;
    
    // We enable the first track, which has the id zero
    videoPlayer.EnableAudioTrack(0, true);
    
    // ...and we set the audio source for this track
    videoPlayer.SetTargetAudioSource(0, audioSource);
    
    // now set an url to play
    videoPlayer.url = "...some url..."
    Aftwards, in a coroutine, prepare and play:

    Code (CSharp):
    videoPlayer.Prepare();
    
    while (!videoPlayer.isPrepared) {
        yield return new WaitForEndOfFrame();
    }
    
    videoPlayer.Play();


Out of time for:
* names above players
* 360 video capture in scenes

Perhaps I'll find time to add these during the week.

The 360 videos, in particular, would be helpful for the students to document the work.



