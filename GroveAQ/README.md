# Arduino + Grove Shield + Air-Quality sensor array
    
**First things first:**

* _This example is NOT a replacement for a certified smoke detector installed by a licensed electrician.
It provides uncalibrated measurements which may be useful for non-essential monitoring, but is entirely inappropriate for 
a stand-alone alarm system._
    
Start with:

- [Arduino UNO](http://arduino.cc/en/Main/arduinoBoardUno)

- [Grove Shield](http://www.seeedstudio.com/wiki/Grove_-_Base_Shield_V1.2)

- [Ether Shield](http://arduino.cc/en/Main/ArduinoEthernetShield)

**OR**

- [Arduino Ethernet](http://arduino.cc/en/Main/ArduinoBoardEthernet)

- [Stacking headers](http://www.adafruit.com/products/85)

- [Grove Shield](http://www.seeedstudio.com/wiki/Grove_-_Base_Shield_V1.2)

**OR**

- [EtherMega](http://www.freetronics.com/products/ethermega-arduino-mega-2560-compatible-with-onboard-ethernet)

- [Stacking headers](http://www.adafruit.com/products/85)

- [Grove Shield](http://www.seeedstudio.com/wiki/Grove_-_Base_Shield_V1.2)

**AND** these sensors:

- [A0 - Grove Gas Sensor (MQ9)](http://www.seeedstudio.com/wiki/Grove_-_Gas_Sensor)

- [A1 - Grove Gas Sensor (MQ2)](http://www.seeedstudio.com/wiki/Grove_-_Gas_Sensor)

- [A2 - Grove Air Quality Sensor](http://www.seeedstudio.com/wiki/Grove_-_Air_Quality_Sensor)

- [A3 - MICS NO2 Sensor](http://www.cdiweb.com/ProductDetail/MICS2710-SGX-Sensortech-Limited/333415/)

- [A4 - Grove HCHO Sensor](http://www.seeedstudio.com/wiki/Grove_-_HCHO_Sensor)

- [D6 - Grove Flame Sensor](http://www.seeedstudio.com/wiki/Grove_-_Flame_Sensor)

Also, import this [library](http://www.seeedstudio.com/wiki/File:AirQuality_Sensor.zip) into Arduino.

You **will** need to power the Arudino via mains, not USB --
the ethernet/sensor draw is more than a USB-powered Arduino can deliver!

This is probably overkill, _groovy!_

Note that when the AQ sensor starts,
it takes 20 seconds before returning control back to `setup()`.
    
A report via the TSRP looks like the following.
Note that the properties are mostly defined as 'epsilon',
which means that the sensors are reporting uncalibrated data,
and `node-homework` will report the current value relative to the standard deviation of the data series.

        {
          "path": "/api/v1/thing/reporting",
          "requestID": "1",
          "things": {
            "/device/climate/grove/air-quality": {
              "prototype": {
                "device": {
                  "name": "Grove Air Quality Sensor Array",
                  "maker": "Seeed Studio"
                },
                "name": "true",
                "status": [
                  "present",
                  "absent",
                  "recent"
                ],
                "properties": {
                  "aqi": "epsilon",
                  "flame_detected": "boolean",
                  "smoke": "epsilon",
                  "co": "epsilon",
                  "no2": "epsilon",
                  "hcho": "epsilon"
                }
              },
              "instances": [
                {
                  "name": "Air Quality Sensor",
                  "status": "present",
                  "unit": {
                    "serial": "deadbeefff01",
                    "udn": "195a42b0-ef6b-11e2-99d0-deadbeefff01-air-quality"
                  },
                  "info": {
                    "aqi": 140,
                    "flame_detected": false,
                    "smoke": 0.9629,
                    "co": 0.0919,
                    "no2": 2.3903,
                    "hcho": -1.2032
                  },
                  "uptime": 14815
                }
              ]
            }
          }
        }
