---
layout: default
title: "Entomology Monitoring Update"
date: 2021-10-03
---

I finished the [previous post](/2021-09-28-entomology-monitoring-with-arduino.md) vowing to investigate alternative dashboard
options, as Blynk had fallen short of expectations. I've since discovered [ThingsBoard](https://thingsboard.io), an Open Source
platform for managing and displaying data from IoT devices, and so far, it looks good.

To create the dashboard, I initially worked through the "Hello World" example, creating a simple dashboard with simulated temperature data.
The UI presents a lot of features, but is not overly complicated, and I was soon able to set things up to my liking.

While the original code written for the Arduino Pro Mini initially worked with the ESP8266 board, some additional libraries
were required to run the wireless on the new board and connect and send data to the ThingsBoard dashboard, so there have been
some updates to the [code](https://github.com/obsidiangecko/entomology-monitor). I worked through some of the starter project code
on the ThingsBoard website to get things up and running, and while I had a few errors in the code to work through, I was able
eventually able to upload the sketch to the microcontroller.

Once that was done, live temperature data from the microcontroller displayed on the dashboard automatically, as I'd used the same
token in the code. From there, adding additional charts to the dashboard and integrating the humidity data was very intuitive, and 
I very quickly had a result.

![ThingsBoard Dashboard](/assets/images/Dashboard.jpg)

This is currently running on the ThingsBoard Demo Server, and so there's some tidy up work to do. As there's no way to act
upon the temperature and humidity data when outside the range of the wireless network, it's not necessary to have access in the
cloud, so my intention is to set up a local ThingsBoard server so I can have complete control over it.

The microcontroller is currently being powered by a USB backup battery, which is quite unwieldy compared to the size of the
rest of the setup, so on the hardware side the next step is to connect a small power supply. Some kind of enclosure may follow
but first I will need to test the ability of the setup to connect with the wireless network from inside the entomology box. 
The network is already running on 2.4Ghz, rather than dual band or 5Ghz, which gives us every chance of success, but I'm prepared
for a problem.