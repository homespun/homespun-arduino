# homespun-arduino

This repository contains [Arduino sketches](https://www.arduino.cc/en/Tutorial/Sketch) that read sensors residing on an
[Arduino Ethernet](https://www.arduino.cc/en/Main/ArduinoBoardEthernet)
and transcodes them to [TSRP](http://thethingsystem.com/dev/Thing-Sensor-Reporting-Protocol.html).
You should review the [homespun root](https://github.com/mrose17/homespun) in order to understand home this repository fits into
the homespun family.

In brief,
you need to be running a process on your home network that listens for TSRP traffic,
and then feeds it to a server that listens for TSRP and uploads the sensor readings to the management cloud of your choice --
here's [my choice](https://github.com/homespun-wink).

The examples in this repository were taken from
[here](https://github.com/TheThingSystem/steward/tree/master/things/examples/arduino),
and then slightly modified for use with the homespun family.

The examples here are:

* [GroveAQ](Grove/README.md)

* [VentSensor](VentSensor/README.md)

* [WaterSensor](WaterSensor/README.md)
