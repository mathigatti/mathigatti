---
title: midi2text & midi2image
date: 2019-06-02 11:54:47
tags:
summary: Being able to convert midi files into text and images allows you to use regular neural networks to generate music. These are some scripts I produced in order to do that
description: Being able to convert midi files into text and images allows you to use regular neural networks to generate music. These are some scripts I produced in order to do that
---

# MIDI to Image conversion

Convert MIDI files into piano roll images and back with this Python script. Full code [here](https://github.com/mathigatti/midi2img).

## Demo
[Here](https://www.youtube.com/watch?v=YJ-TEpLwuns) is a video demonstration using the program to generate midis and images, then we use it for an artistic performance.

[![IMAGE ALT TEXT HERE](https://i.ytimg.com/vi/YJ-TEpLwuns/maxresdefault.jpg)](https://www.youtube.com/watch?v=YJ-TEpLwuns)


# MIDI to text conversion

People like [Gwern](https://www.gwern.net/GPT-2-music#) and [Shawn Presser](https://soundcloud.com/theshawwn/sets/ai-generated-videogame-music) used [ABC notation](https://en.wikipedia.org/wiki/ABC_notation) to convert midi files into text. I thought it was too verbouse so I tried my own.

- [midi2text](https://gist.github.com/mathigatti/fb31ef7f82b7ef822e1630c2dfea86b0)
- [text2midi](https://gist.github.com/mathigatti/7fdafc0f4fbeb5353b567905389ea2b8)