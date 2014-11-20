---
layout: minimal_project
project: True
title: APRS Weather Box
introduction: A simple arduino project collecting weather data and sending as APRS beacons.
ghlink: https://github.com/yangl1996/aprswxbox
---
### Overview

APRS is an open AX.25 (an amateur radio packet data transfer protocol) network started by Bob (WB4APR) and operated by amateur radio operators all over the world.

This project turns an Arduino board into a simple weather station which collects temperature, humidity and barometric pressure. It sends data every 10 minutes to the APRS-IS (Internet Service) server. All you need to build a weather station are an Arduino board, a W5100 Ethernet Shield, a DHT21 temp/humidity sensor and a BMP085 barometric pressure sensor. For detailed info about building and troubleshooting, feel free to contact me.

The project is coded by Weng Kai (BA5AG) and me. The source code is on [GitHub](https://github.com/yangl1996/aprswxbox).

### Preparation for a Weather Station

* a Mac or a PC
* Arduino IDE (ver 1.00 or later) installed on your computer
* a USB cable
* a router
* a power supply
* an Arduino board
* a W5100 Ethernet Shield
* a DHT21 sensor
* a BMP085 sensor

### How to build

Setting up an APRS Weather station is as easy as connecting a few wires. It takes about 15 minutes to complete the whole process. Just follow the guide below.

First, connect the Ethernet Shield to the Arduino board. Connect the Arduino to a computer and load the code. You need to modify the code to make it sending beacons with your call sign and location. Edit "callsign", "passcode" and "location". "Passcode" is a unique 5-dig number that is paired with your callsign to verify your identity as an amateur radio operator. If you haven't got one, there're many HAMs who provide free passcode calculating. As for location, you may check Google Maps or other map service. Be sure to enter your location in the correct format (like the default location data in the code). Last, change the APRS-IS server address if needed (e.g. when the default server is down).

Then, plug the two sensors into proper pins shown in the connection graph. This step may be a little frustrating.

Third, connect the Weather Box to your router. Plug in the power. Check if your station "CALLSIGN-13" is shown properly on the APRS-IS network (e.g. check aprs.fi and search for your callsign). Then check whether the weather data are correct. If not, try to follow the troubleshooting guide below.

### Note

When building an APRS Weather Box, you should only use DHT library download from my repository ([HERE](https://github.com/yangl1996/DHT-sensor-library)) because we have modified the original library. So the original library will NOT work. And also get the BMP library from my repository.

Thanks to Carl Davies (M1ELR) from the UK for submitting these issues.

### Troubleshooting

If your Weather Box doesn't work or doesn't work properly, try to follow these instructions.

1. Connect your Weather Box to your computer with Ethernet cable plugged in.
2. Open Serial Monitor in the Arduino IDE.
3. Turn on the power.
4. Check the message shown in the Serial Moniter window.

* DHT fail - The DHT sensor fails or there are some connection errors with your sensor. Check the connection or replace the sensor.
* Can not connect to the server - The Box can't connect to the APRS-IS server. Check the network connection and whether you entered the correct APRS-IS server address.
* No prompt from the server - The server is down. Maybe try again later.
* Login failed - Can't login to the server. Check the call sign and the passcode.

If you are still stuck with Weather Box, feel free to contact me.

### Resources

A connection graph and the source code are available on GitHub. Check them out [HERE](https://github.com/yangl1996/aprswxbox). A review is available in Chinese at [BG5HSC's blog](http://blog.sina.com.cn/s/blog_6ae7f76a0100zm4v.html).

If you have any difficulties building an APRS Weather Box, just email me and I am glad to hear from you! My email address is i@yangl1996.com
