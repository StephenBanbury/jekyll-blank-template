---
layout: post
title: Building The Apps
date: 2020-10-01 03:00
published: true
---

# Audience - Oculus Quest

# Performer Main Room - PC/Mac

PC build works. 
Mac build creates exceptions - I believe these can be traced to requirements for the **info.plist** - i.e. requesting permissions

> Microphone class is used but Microphone Usage Description is empty. App will not work on macOS 10.14+.

Search leads to responses such as [You need to add a microphone usage description string in iOS Player Settings (which will be added to your Info.plist)](https://answers.unity.com/questions/1735434/build-error-microphone-class-is-used-but-microphon.html)

[Requesting Authorization for Media Capture on macOS](https://developer.apple.com/documentation/avfoundation/cameras_and_media_capture/requesting_authorization_for_media_capture_on_macos?language=objc)


I need the mike, so this is a requirement.

I found all files named info.plist and added the line, where it was missing:

> <key>NSMicrophoneUsageDescription</key>
> <string>Yes</string>

However, this did not work - I still get the microphone error.

# Performer Video Streaming - PC/Mac

# Stage Manager OSC Controller - PC/Mac

The PC apps need to be built for Mac - it seems the world of Theatre runs on Macs!


