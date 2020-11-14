---
layout: post
title: Streaming And Displaying Video Clips
date: 2020-10-31 00:00
published: true
---

# Partial Solution 1

I have discovered that video files can be streamed from **[Dropbox](https://www.dropbox.com/)** if the URL is ameneded slightly. The URL is accessed by using the **dropbox** 'share' function from the right-click on the file. 

* Change _'www.dropbox.com'_ to _'dl.dropbox.com'_
* Remove the querystring _'?dl=0'

**NB** the URL is automatically modified by dropbox from to _dl.dropboxusercontent.com_.

I have added a service class that reads a locally-stored text file listing the dropbox URLs (they are amended according to the above rules if necessary).

I would dearly love to place this file in the **dropbox** folder and read it from there. This will allow the students to add files to the folder and then amend the text file in order for it to be included. However, the **dropbox** API is not as straightforward as I would have liked. There is a SDK for .**NET**, but it does not work with Unity (ref). 

It would, of course be possible to spend some time building a bespoke method to access the dropbox API, but I'm concerned about the amount of time this would take. 

# Partial Solution 2

Taking the dropbox plan and running with it, I have created a **_Firebase_** _Realtime Database_ to store the URLs for the videos. I have then implemented a **_REST API_** client in order to access them. 

**NB** _The reason for the REST is that I have previously had problems getting Firebase's Unity SDK to work with Android. I believe that, at the time, it was not compatible, but current research, and the SDK's documentation, seems to suggest that ([Android has now been incorporated](https://firebase.google.com/docs/unity/setup)). However, as I know that the Rest API works, for the time being I will use this._

For the time being, students will need to access the _shared link_ from Dropbox for each video, pass it on to me and I will place it in the database.

**The important and urgent thing** is that the students can use their own content, so this solution will be very welcome as it enables this. Further development will include provision for the students to upload and to manage the database themselves.

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\GAM750\create-dropbox-link.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

