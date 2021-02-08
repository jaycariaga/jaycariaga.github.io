---
layout: post
title:  "Making an Audio Visualizer with ws2812b!"
date:   2021-01-08 15:35:31 -0500
categories: jekyll update
---
Hello fellow reader,

Note: You can also follow my github repo on projects like this here: [Github: Arduino-Projects][Arduino-Link]. Go to /src/ws2812bAudioReactive.ino to view the code for this.

First things first, I would like to list out the general application of this mini-project: 
1. The main goal here is to take surrounding noise and sound and create an interactive rgb lighting experience.
2. Necessary components used: Arduino (Uno was used here but anything of the like is fine as well), a 300-500 Ohm resistor, a ws2812b led strip, and a MAX9814 microphone. 
3. This setup currently only supports interaction with the AMPLITUDE of the entire mic's output signals, thus not based on a specific set of frequencies
4. Code's variables are editable to suit better for specific types of noise environment (ex. tempo, overall loudness)
5. Currently working on: multiple settings for light effects like solid colors, specific color change settings, e.t.c. 

In terms of editable code to the user's liking, I would suggest only looking at these specific global variables:
{% highlight ruby %}
#define NUM_LEDS 60 // How many leds in your strip?
#define DATA_PIN 6 // For led chips like Neopixels, which have a data line, ground, and power, you just need to define DATA_PIN. 
#define minima .11 //the higher the less sensitive
#define slowness 1 //the higher the slower hues change
const int sampleWindow = 40; // Sample window width in mS (40 mS = 20Hz)
{%endhighlight%}

In the future, I would like to implement a switch system that changes the type of lighting structure besides the hue cycle capability.  Possibly going for solid color changes, or different lighting styles for audio visualizing.  

[Arduino-Link]: https://github.com/jaycariaga/Arduino-Projects