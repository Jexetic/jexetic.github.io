---
title: "Automating Alexa-enabled devices with iOS Shortcuts"
date: 2024-01-23T15:03:21-07:00
tags: [tech]
draft: false
---

If you’re buying smart home stuff, chances are it works with Alexa. Personally, I have bought a few Govee light strips and outlets, and they work great with Alexa. The thing is, I wanted them to turn on when my iPhone’s alarm went off to help me wake up.

Most current Govee products are not HomeKit compatible. I also don’t have an Apple TV or a HomePod to use as a hub for HomeKit. They do work with iOS Shortcuts, but unfortunately I could not seem to get them to work with the automations portion of the Shortcuts app. The solution I ended up going with is to run an Alexa routine when my phone alarm goes off.

To achieve this, I used an Alexa skill called [Voice Monkey](https://voicemonkey.io/ "https://voicemonkey.io/"). Voice Monkey allows you to make things called Routine Triggers, which appear as virtual devices Alexa can see. You can then create routines that run when these virtual devices are activated.

So, I created a trigger called iOS Alarm. These triggers can be activated with an API, so I made an iOS Shortcut with the “get contents of URL” action and put in the URL Voice Monkey gave me for my trigger. Then, I told iOS to run that shortcut when my alarm goes off. The first time you run the shortcut, you’ll have to give it permission to access the Voice Monkey URL. After that, it will run seamlessly in the background.

In the future I will probably look into something like Home Assistant, but this is a nice band-aid solution to automate things with iOS for now since I don’t want to invest in HomeKit.