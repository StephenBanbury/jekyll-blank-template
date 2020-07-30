---
layout: post
title: Building A WebRTC Web App
date: 2020-07-27 23:00
published: true
---

As stated in the previous post, at the moment **I feel that my time would be best spent learning about WebRTC in general, rather than  specifically as a Unity plugin**. Once I feel I fully understand the basics I should be able to apply them more easily to my specific Unity test-case.

I have found a useful-looking half-hour-long YouTube tutorial, **[How To Create A Video Chat App With WebRTC](https://www.youtube.com/watch?v=DvlyzDZDEq4)**. It was only published a day ago but has already received over 2,000 'likes' (and only 15 thumbs-down). If nothing else, I see this as further evidence of the current, pandemic-induced social lockdown interest in the subject of peer-to-peer video chat apps.

I have also placed a tutorial into my Udemy Cart and may decide to purchase it. I have 10 hours to get it at the discount price of £13.99 (reduced fro £49.99, apparently). But first I will see what the free YouTube offering is about.
* I note the many cricisms in the review/comments section that this course is out of date, is deprecated and not been updated for three years. This may be unfair, but I think I'll just find what I need for free on YouTube etc.

# Notes on setting up the WebRTC project

Setting up the server

**npm i express ejs socket.io**

* Use the [Expressjs server](https://expressjs.com/): [expressjs.com/installing](https://expressjs.com/en/starter/installing.html), [npm](https://www.npmjs.com/package/express), 
* use dependency ejs - templating language / view engine
* use socket.io
* uuid

**npm i uuid**

* allows us to create dynamic IDs for different rooms

**npm i --save-dev nodemon**

* Dynamic refreshing of server on making changes

**server.js**

    const express = require ('express')
    const app = express()
    const server = require ('http').Server(app)
    const io = require('socket.io')(server)
    const { v4: uuidV4 } = require('uuid')

    app.set('view engine', 'ejs')
    app.use(express.static('public'))

    app.get('/', (req, res) => {
        res.redirect(`/${uuidV4()}`)
    })

    app.get('/:room', (req, res) => {
        res.render('room', { roomId: req.params.room })
    })

    server.listen(3000)

**room.ejs**

**Note**: you can use ! in a new file to generate HTML boilerplate code.

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <style>
            #video-grid {
                display: grid;
                grid-template-columns: repeat(auto-fill, 300px);
                grid-template-rows: 300px;
            }
            video {
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
        </style>
    </head>
    <body>
        <div id="video-grid"></div>
    </body>
    </html>


**So far we have a server that generates a random room (with a random ID) everytime localhost:3000 is called**. The room page contains a blank div which will hold the video.

**Add joining room function to server.js**

    io.on('connection', socket => {
        socket.on('join-room', (roomId, userId) => {
            console.log(roomId, userId)
        })
    })

**roomId** is set as a constant in the JavaScript so is sent to the page

    <script>
        const ROOM_ID = "<%= roomId %>"
    </script>

![roomId sent to the page](/images/gam750/webrtc-roomid.jpg)

**Bring in the socket.io jasvascript code into our front end, served by our own server (server.js)**

    <script src="/socket.io/socket.io.js" defer></script>

**Add a script file for our own JavaScript**

    <script src="script.js" defer></script>

**Join room and broadcast userId to other clients**

.. in **script.js** (userId is hard-coded for now)

    const socket = io('/')

    socket.emit('join-room', ROOM_ID, 10)

    socket.on('user-connected', userId => {
        console.log('User connected: ' + userId)
})

.. in **server.js**

    io.on('connection', socket => {
        socket.on('join-room', (roomId, userId) => {
            socket.join(roomId)
            socket.to(roomId).broadcast.emit('user-connected', userId)
        })
    })


**When the second client joins the same room (same roomId) the first client is informed**
![joining the room](/images/gam750/webrtc-join-room-1.jpg)

# PeerJS

**npm i -g peer**

**[The PeerJS library](https://peerjs.com/)** allows us to run a **peer server**, creating connections between different users using WebRTC.
  * Note - I'm hoping this is not going to prove to be a difficult part of the process of setting up WebRTC for Unity.

**peerjs --port 3001**

The peer server is now runing on poer 3001, which will allow us to connect users and will give us an ID to replace the hard-coded one above.

Add the following (from https://peerjs.com/) to **room.ejs** (using defer to ensure running first)

    <script defer src="https://unpkg.com/peerjs@1.3.1/dist/peerjs.min.js"></script>

**Place the emit function (in script.js) into a function to run when connected to PeerJS**

This will provde the unique ID for the user that is connected.

    myPeer.on('open', id => {
        socket.emit('join-room', ROOM_ID, id)
    })

**Get a reference to the video grid**

    const videoGrid = document.getElementById('video-grid')

**And a reference to a video** and mute it so we don't hear our own voice played back to us.

    const myVideo = document.createElement('video')
    myVideo.muted = true;

**Connect our video**, returns a stream (as a promise), which will be listened to by an event listener (see function addVideoStream below)

    navigator.mediaDevices.getUserMedia({
        video: true,
        audio: true
    }).then(stream => {
        addVideoStream(myVideo, stream)
    })

    Function addVideoStream(video, stream){
        video.srcObject = stream
        video.addEventListener('loadedmetadata', () => {
            video.play()
        })
        videoGrid.append(video)
    }

**On refreshing our page, we can see our video appear in our page**

Permissions will be required the first time this is run.

**Allowing ourselves to be connected to by other users**

Send our current video and audio stream to the new user

    socket.on('user-connected', userId => {
        connectToNewUser(userId, stream)
    })

When they call back we take in their video stream - called 'stream' - [ call.on('stream',... ] and add to our list of videos [ addVideoStream(video, userVideoStream) ]

**On close, remove the video from the page.**

    function connectToNewUser(userId, stream) {
        const call = myPeer.call(userId, stream)
        const video = document.createElement('video')
        call.on('stream', userVideoStream => {
            addVideoStream(video, userVideoStream)
        })
        call.on('close', () => {
            video.remove()
        })
    }

We must listen for calls so we know if someone is calling us and then we can add them to our videos on screen.

    myPeer.on('call', call => {
        call.answer(stream)
    })

But we need to respond

        const video = document.createElement('video')
        call.on('stream', userVideoStream => {
            addVideoStream(video, userVideoStream)
        })

So now we can receive calls by listening to our **on call event** and make calls when new users connect to our room (connectToNewUser)

**Finally we need to handle closing the videos better when a user disconnects**

Back in **server.js**, on disconnect run another function (broadcast.emit) to send the event down to our room.

    socket.on('disconnect'), () => {
        socket.to(roomId).broadcast.emit('user-disconnected', userId)
    }

then to pick up this event in script.js

    socket.on('user-disconnected', userId => {
        console.log(userId)
    })

We need to use the userId to disconnect the user

We can log the callers in an object

    const peers = {}

and on connecting to new user add them to the object so they can be removed when disconnected

    peers[userId] = call

    socket.on('user-disconnected', userId => {
        if(peers[userId]) peers[userId].close()
    })

<figure class="video_container">
  <video style="width:720px;" autoplay loop>
    <source src="\media\webrtc-javascript-1.mp4" type="video/mp4">
    Woops! Your browser does not support the HTML5 video tag.
  </video>
</figure>

# All the scripts in their entirety

**server.js**

    const express = require ('express')
    const app = express()
    const server = require ('http').Server(app)
    const io = require('socket.io')(server)
    const { v4: uuidV4 } = require('uuid')

    app.set('view engine', 'ejs')
    app.use(express.static('public'))

    app.get('/', (req, res) => {
        res.redirect(`/${uuidV4()}`)
    })

    app.get('/:room', (req, res) => {
        res.render('room', { roomId: req.params.room })
    })

    io.on('connection', socket => {
        socket.on('join-room', (roomId, userId) => {
            socket.join(roomId)
            socket.to(roomId).broadcast.emit('user-connected', userId)

            socket.on('disconnect', () => {
                socket.to(roomId).broadcast.emit('user-disconnected', userId)
            })
        })
    })

    server.listen(3000)

**room.ejs**

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <script>
            const ROOM_ID = "<%= roomId %>"
        </script>
        <script defer src="https://unpkg.com/peerjs@1.3.1/dist/peerjs.min.js"></script>
        <script src="/socket.io/socket.io.js" defer></script>
        <script src="script.js" defer></script>
        <title>Document</title>
        <style>
            #video-grid {
                display: grid;
                grid-template-columns: repeat(auto-fill, 300px);
                grid-template-rows: 300px;
            }
            video {
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
        </style>
    </head>
    <body>
        <div id="video-grid"></div>
    </body>
    </html>

**script.js**

    const socket = io('/')
    const videoGrid = document.getElementById('video-grid')
    const myPeer = new Peer(undefined, {
        host: '/',
        port: '3001'
    })
    const myVideo = document.createElement('video')
    myVideo.muted = true;
    const peers = {}

    navigator.mediaDevices.getUserMedia({
        video: true,
        audio: true
    }).then(stream => {
        addVideoStream(myVideo, stream)

        myPeer.on('call', call => {
            call.answer(stream)
            const video = document.createElement('video')
            call.on('stream', userVideoStream => {
                addVideoStream(video, userVideoStream)
            })
        })

        socket.on('user-connected', userId => {
            connectToNewUser(userId, stream)
        })
    })

    socket.on('user-disconnected', userId => {
        if(peers[userId]) peers[userId].close()
    })

    myPeer.on('open', id => {
        socket.emit('join-room', ROOM_ID, id)
    })

    function connectToNewUser(userId, stream) {
        const call = myPeer.call(userId, stream)
        const video = document.createElement('video')
        call.on('stream', userVideoStream => {
            addVideoStream(video, userVideoStream)
        })
        call.on('close', () => {
            video.remove()
        })

        peers[userId] = call
    }

    function addVideoStream(video, stream){
        video.srcObject = stream
        video.addEventListener('loadedmetadata', () => {
            video.play()
        })
        videoGrid.append(video)
    }

**Run with..**

    npm run devStart

**which runs the script in package.json**

    "scripts": {
      "devStart": "nodemon server.js"
    },


## Conclusion

This has been an interesting and valuable lesson in peer-to-peer connectivity. I am still not sure I have much of a handle on WebRTC specifically as, unexpectedly, the project uses **[Peer JS](https://peerjs.com/)**, an external JavaScript library to provide an API to handle WebRTC.

However, I am probably - hopefully - in a better position to attempt implementing WebRTC in a Unity project.
