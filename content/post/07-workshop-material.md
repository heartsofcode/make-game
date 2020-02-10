---
title: "Arduino workshop material"
slug: arduino-workshop-material
date: 2020-02-10
categories:
- fyi
tags:
- arduino
---

I decided to start working on workshop material for the [Intro to Arduino workshop](/event/intro-arduino/) in March. The material will be web based and available online, you can find the [repository on GitHub](https://github.com/heartsofcode/ws-intro-arduino).

As for the tech stack, I chose [mdbook](https://rust-lang.github.io/mdBook/) which I wanted to try for some time. You can also deploy it with [Netlify](https://netlify.com/), I'll paste the one-liner to also fetch the mdbook binary here (also for my future self).

``` bash
curl -L https://github.com/rust-lang/mdBook/releases/download/v0.3.5/mdbook-v0.3.5-x86_64-unknown-linux-gnu.tar.gz -o dl.tar.gz; tar xzf dl.tar.gz; ./mdbook build
```

You can follow the progress of (and of course, just read) the material here [//arduino.makeandga.me](https://arduino.makeandga.me/).

Cheers!
~  lislis
