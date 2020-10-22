---
layout: post
title: The Possibilities Of OSC
date: 2020-09-13 01:00
published: true
---

# OSC Controller

![Formation 5](\images\GAM750\osc-interface-2.JPG)

I created an Unity project for the purpose of developing an _OSC controller_. After importing the **OSC Simpl** Unity package, I studied the example apps and the documentation - which is concise but not rich enough to rely on without a fair bit of code-analysis - and managed to cobble together an OCS controller with buttons that replace the temporary VR interface I have been using to control the environment from within.

The main app also contains the OSC package and listens for OSC data messages. Once received, the message fires exactly the same actions as the temporary interface. Therefore, the desired effects not only occur, but they sync across _Normcore_.

Currently, the OSC messages are in the form: -

* /select/video
* /select/stream
* /select/display
* /select/formation

The /select/ part indicates that a selection has been made.
/video/, /stream/ etc. indicates what kind of action we are going to request.

Following this, an argument is passed indicating the **ID** of the video, the video stream, the display screen, or the screen formation...

        const string _videoSelectAddress = "/select/video";
        const string _streamSelectAddress = "/select/stream";
        const string _displaySelectAddress = "/select/display";
        const string _formationSelectAddress = "/select/formation";

        public void VideoSelect(int videoId)
        {
            oscOut.Send(_videoSelectAddress, videoId);
		    }
        public void StreamSelect(int streamId)
        {
            oscOut.Send(_streamSelectAddress, streamId);
        }
		public void DisplaySelect(int displayId)
        {
            oscOut.Send(_displaySelectAddress, displayId);
		    }
        public void FormationSelect(int formationId)
        {
            oscOut.Send(_formationSelectAddress, formationId);
        }

... and at the listening end, these patterns are looked for and responces are wired up. Therefore a specific message plus arguments is sent, and this results in a specific method being called at the receiver's end.

![OSC Interface](\images\GAM750\osc-interface-1.JPG)

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\osc-unity-demo-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\osc-demo-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>


# Should be fun

Of course, this follows the pattern already in place in the main VR app, i.e. when selecting the video or stream to display, the ID is selected first, followed by the ID of the display on which the respective media is to be shown. 

However, as suggested by my fellow student and resident OSC expert, Sam Smallman, on our Discord server forum, there are other possible ways to provide this information: -

> **Sam:** You can use wildcards to help so you would basically receive an OSC message and pattern match for "/fireclown/screen/*/hidden" then you would grab the 3rd part which would be the screen number and then take the argument value and hide unhide the screen from there.

> Have you considered stateless commands, so /formation 3 "1 2 3 4 5", basically set formation to 3(1st argument) to the screens 1 thru 5 (2nd string argument)

> then you could have /screen/1/formation 3, to set indivual screen 1 to formation 3
.. ah no because formation is a global thing but video feed, /screen/1/video 3, to set indivdual screen 1 to video feed 3. There's a lot of fun you can have with this

> **Me:** My big issue, though, is how to set it up to send over the internet. Probably have to send it via Agora - which I'm using for the video streaming but also has a data channel - or normcore somehow... I think you've mentioned before that theatre is usually done in a closed network.

> **Sam:** it might be easier to just send http post requests with a json packet as the arguments, and then you can translate them to osc

> oh yeah, most theatre wont be online ever. Things are changing at the moment but still there's massive superstition about putting anything online during a performance.

> **Me:** As this project is all about remote working, I have no choice in the matter.

> **Sam:** you would need to wrap osc anyway to get over the net you may aswell just wrap it in http

> as a theatre practitioner my next questions would be what control over the screens do i have. Does screen feeds snap from one to another, do i have control of fading it,  do i have control of the formations and how they move from one to another and the time they take, can i indivdually control screen brightness etc. All of that I would want control via OSC arguments etc.


So I'm going to have fun with OSC once we've nailed down the requirements and in what contexts we think it could be most useful. I think the main difficulty will prove to be finding the best (and, as always, the least time-consuming) way to get the data across the internet. I feel this may best be achieved by including Agora or Normcore in the OSC project and sending the data wrapped in JSON to the main VR app. Once it has arrived, it can then be interpretted and acted upon. 

In a way, this will negate the need for the OSC Simple package, as there will likely be no need to broadcast via http and listen at the other end. However, it could be more flexible in the long run to use as much of the basic OSC broadcasting pattern and the technology behind it as possible, and as little as possible of the mechanism used to send the data occross the _World Wide Web_.

