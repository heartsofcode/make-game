---
title: "js13k submission"
slug: js13k-submission
date: 2019-09-16
categories:
- status
tags:
- game jam
- a-frame
- web
- vr
---

The jam is over! And I [submitted backstreetsback in time](https://js13kgames.com/entries/backstreetsback). Yay!

<!--more-->


Also, the [repo changed](https://github.com/lislis/entry-backstreetsback) because I tried to make the entry submission-ready and I was tired and couldn't focus and apparently forgot that `git remote add` exist ??? (don't stay up late and code, kids!). The reason being that the jam [created a very neat bot](https://github.com/js13kGames/bot) to check pull-requests for formal validity. It was an optional check this year, but I can see how this will be mandatory next year as it removes a lot of manual requirement checking. Automate all the things!

## Lyrics design

Anyway, back to the content of the game!

After a short brainstorm at Damensalon two weeks ago, I settled on having the lyrics of *Everybody* displayed on some sort of poster, that will rotate and fade out when you 'clicked' it.

I also decided to have it read by the [Web SpeechSynthesis API](https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis), and add a 'Yeah!' after every snippet for fun. (The fun being, sometimes the 'yeah' is appropriate, sometimes it's not.)

It's also only a few lines of code to get it set up

``` js
var synth = window.speechSynthesis;
var voice = synth.getVoices()[1]; // or whatever index

// ... then in the poster component event handler

var utterThis = new SpeechSynthesisUtterance(this.getAttribute('text')['value']); // this is where I get the actual tetxt from a poster
utterThis.voice = voice;
synth.speak(utterThis);
```

Very cool! Plus, different browsers on different devices seem to have different voices. On my testing smart phone running firefox I got a woman with Russian accent reading Backstreet Boys. Hilarious!

## Dun, dun dun dun dun dun dun

There is also music! It's a small looping pattern that aims to imitate the main theme from Everybody.
I used [TinyMusic](https://github.com/kevincennis/TinyMusic) as library for a bit of abstraction over the web Audio API and defined a pattern like so:

``` js
var sequence = new TinyMusic.Sequence( ac, tempo, [
      'B3 e',
      '- e',
      'B3 e',
      'A#3 e',
      'A3 e',
      'G#3 e',
      'G3 e',
      '- e',
      'G3 e',
      '- e',
      'G3 e',
      'A3 e',
      'F#3 e',
      '- h'
    ]);
```

That's all! Just the kind of notation you want! I'd definitely use this again!


## Fingers crossed

Well, let's see how the voting goes! The webXR category has 28 submissions, so I think there is a realistic change I can make the top 10 🤞

Now that the jam is over, I'll go back to Godot and Arduino! Or maybe Rust, let's see.

I'm also thinking of working on some workshop material for getting started with electronics and Arduino and sensors, but that needs some more thinking.


~ lislis
