---
layout: post
title: 
date: 2020-05-16 13:37:00 +0100
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: Adding-a-virtual-sound-device-to-ESXi.png # Add image post (optional)
tags: [VMware, ESXi, Audio, Windows, Commodore 64, WinVICE, Twitch, Ultimate64] # add tag
---
While I want to stream audio and video from my Commodore 64, actually an Ultimate64, I stumbled across the absence of audio on a virtual machine running on my lab system.

Essentially I needed to manually edit the VM context. 

Following this procedure:
M
*	Make sure that the VM is in a powered-off state
*	Browse to the datastore where the VM resides
*	Download the <InsertVirtualMachineName>.VMX file
*	Edit file by adding the undermentioned lines to the end of the file

	```Startup the VM again
	sound.present = "true"
	sound.allowGuestConnectionControl = "true"
	sound.virtualDev = "hdaudio"
	sound.fileName = "-1"
	sound.autodetect = "true"
	sound.pciSlotNumber = "34"```

*	Upload the file again to the same spot in the datastore


Now the VM can play audio again. In my case i can  record/stream audio to [my Twitch channel](https://www.twitch.tv/berrydejager).