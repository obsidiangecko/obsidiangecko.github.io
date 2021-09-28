---
layout: default
title: "Entomology Monitoring with Arduino"
date: 2021-09-28
---

This [project](https://github.com/obsidiangecko/entomology-monitor) is still in progress, because, well, I'm not happy yet.

The idea is to monitor the temperature and humidity inside a sealed box, which is being used to prepare entomological specimens for
display mounting. The environment needs to be kept stable within certain paramaters, and so this seemed like a great excuse to break
out the Arduino Pro Mini type controllers I've been hoarding. First up, I needed to solder the headers on. I have struggled with choosing 
the right soldering irons and solder of late, but finally seem to have the right size of everything for the job, and I was actually quite 
impressed with the quality of the joints, even if the pins were a little splayed and would plug into a breadboard. 

![Solder Joints](/assets/images/solder.jpg)

The DHT11 sensor is well suited to the application, as the target temperature and humidity is well within the range of the sensor,
and it's also small and cost effective. The Pro Mini doesn't have an onboard USB connection, so I needed to connect a serial connector
module in order to program it, to be removed afterwards and replaced with a power supply.

![Pro Mini Setup](/assets/images/ProMini.jpg)

Once connected, I created the basic sketch in the Arduino IDE and was able to get the temperature and humidity readings to print
to the Serial Monitor, so all seemed well. The next step was to investigate wireless communication so that the readings could
be taken from within a sealed box, and it was here that I ran into some difficulty. Wireless modules were much easier and more
cost effective to come by if they were part of the board - enter the ESP8266. While not strictly Arduino, it can be programmed
from the same IDE, and there's a handy DHT11 shield purpose built to plug into it. I had to solder the headers onto the ESP8266,
which I did with the DHT11 shield plugged in, so that the headers were straight, although I noticed that the pins on the DHT11 shield
weren't straight to begin with, so I became a little less critical of my earlier soldering work. The new set up is compact and much tidier.

![ESP8266 with DHT11 shield](/assets/images/ESP8266.jpg)

With the sketch uploaded to the new setup and producing readings, I started looking into communication. [Blynk](https://blynk.io)
looked like a great option. You can create both web and mobile based dashboards to display the data, and Blynk will generate
the default code for connection to your project. After getting connection sorted, I built the dashboards, but I was disappointed
by the range of options available. I wanted to display instantaneous measurements, as well as history, in order to show stability
over time, but Blynk didn't really offer these options. In addition, Blynk seemed to need to run at 115200 baud, where my sketch had previously
run at 9600 baud. Numerous things were thrown out by this, and I needed to run different libraries for the DHT11. I tested a sketch
I found online, and this worked, however I still wasn't happy with the dashboard, so I'm currently looking for an alternative. Uploading
the data to a Google Doc is an option, but not one I'm fond of if dashboards are possible. Building an entire webpage from scratch
seems a little like overkill, as I'm sure something suitable already exists.

Stay tuned!