---
layout: post
title: Sending and Receiveing OSC Data
date: 2020-09-14 01:00
published: true
---

I've been thinking about how to send data between clients. The requirement is to make use of one of the two platforms I have put in place to keep clients connected - i.e. **Normcore** for multiplayer functionality and **Agora** for live video and audio streaming - in order to send simple data that can be used and interpreted in a number of ways, with a number of possible functionalities in mind. 

# OSC addressing
The main one here is **OSC** messages, used to control screen content, formations, lighting, sound, and many other potential uses that could come up as this project continues to be developed. As this data is simply text, it could be passed in form of JSON or raw strings, and then easily interpreted by clients connected in.

But there could potentially be other uses for such data channels. Perhaps they could be used to send _coordinate_ data for the screen formations and, more interestingly, the _players within the VR space_. These could then be used in mappying out the space in _real life_ in order for the performers to keep tabs on where players are and on their movements.

# Agora
**Agora** provides a simple data channel that can be used for sending text messages from broadcaster to clients. I am currently thinking that this could be very useful for sending data in JSON format.

I have tested it with simple _'hello'_ messages.

**Message sent from Video Streaming client and received by VR client**
![message 1](\images\GAM750\agora-data-stream-message-1.JPG)

**Message sent from VR client and received by Video Streaming client**
![message 2](\images\GAM750\agora-data-stream-message-2.JPG)

# Normcore
I am very tempted to hook up both the video streaming and the OSC controller client apps to Normcore and allow data to be pushed around using Normcore data-pooling techniques. This could work in exactly the same as does sending video, screen and screen formation selection currently does between clients that have joined the room. The advantage of this method could be that it would be a relatively simple task to share **all** data that is being used by **all** of the client apps involved. It would not require specific extra channels, methodologies and means of sending and receiving data. The way the data is packaged and then interpreted at the receiving end will be the same, but pooling the data via Normcore will allow it to be accessible by any client at any time.

# Decision
The simplicilty of sending text messages using Agora is tempting me in this direction. There is little to set up and it will not require writing methods to keep the data in sync between clients. 

I feel the way forward will be to include both Normcore and Agora in all three apps, so that any can be called upon where necessary. But for the time being, I will explore the use of Agora's simple messaging ability to for OSC addressing. 

When it comes to finding ways to keep performers (i.e. video streaming clients) informed as to the positioning of audience, it may be that I will turn to Normcore.