---
layout: post
title: "Creating My First Clockface With FitBitOS"
date: 2021-09-15
---

I bought myself a FitBit earlier this year, and one of the major attractions has been the
ability to turn everyday activity into data. A lot of data is either collected or produced
by the FitBit ecosystem, and so combinations of data to display on the watchface are almost 
endless. Finding a pre-built clockface that displays the combination you want, however, is 
not so straighforward. After I a little research, I discovered that FitBit apps and clockfaces
are built in FitBit Studio in a variation of JavaScript, so I decided to try my hand.

I was a little rusty on JavaScript, and needed to learn about the APIs for FitBit devices,
so I found the FitBit Open Source apps list on GitHub. I leaned on the [FitBitOS-Really-Basic](https://github.com/gpfrello/FitbitOS-Really-Basic)
clockface code and comments pretty heavily to learn the ropes.

Once I had the basics, I started to tinker with bringing in additional data from the device
API, and using graphic elements, manipulating the styles.css and index.view files to create
the aesthetic style of the clockface. Other open source clockfaces provided many examples of
how to do similar things in different ways, and so [my own clockface](https://github.com/obsidiangecko/digital-interoception) 
developed from many sources of inspiration. 

![Basic MkII Clockface](https://github.com/obsidiangecko/obsidiangecko.github.io/blob/main/images/Basic-MkII-small.jpg)

In addition to basic date and time, I have displayed heart rate, steps and active zone minutes
in this design. In future iterations, I want to add water consumption to the clockface, however
as this isn't measured by sensors in the watch, the data is accessed via the FitBit Web API,
so the next step is to do more research around that area, where I hope the [Water Logged](https://github.com/tylerl0706/Water-Logged)
code will be of great assistance.
