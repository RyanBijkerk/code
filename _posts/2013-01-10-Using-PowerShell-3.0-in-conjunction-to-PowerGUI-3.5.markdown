---
layout: post
title: 
date: 2014-10-31 13:37:00 +0100
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: Getting-the-keyboard-layout.png # Add image post (optional)
tags: [PowerShell, PoSh, Scripting, Windows] # add tag
---
My favorite editor for PowerShell script is definitely PowerGUI from Quest Software, Inc. This editor is very intuitive and gives you a good overview of the PowerShell environment and extensive debugging features.
Recently I needed to create a script to use with AppV 5.0, which is based on PowerShell 3.0. PowerGUI has extensive support for PowerShell 2.0 and is capable of working with PowerShell 3.0 scripts too. To enable the PowerShell 3.0 support you can use the following application executables, located in the installation folder, parameters:

	AdminConsole.exe –version 3.0
	ScriptEditor.exe –version 3.0
	
For the ease of use you can just alter the shortcut to the following properties:

![Script Editor PowerShell 3.0 Properties](/assets/img/2013-01-10-Using-PowerShell-3.0-in-conjunction-to-PowerGUI-3.5_img00.png)

Enjoy the power and potential from both worlds now!