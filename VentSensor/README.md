# Arduino + Grove Shield + Return Ventilation sensor array

Start with:

- [Arduino UNO](http://arduino.cc/en/Main/arduinoBoardUno)

- [Grove Shield](http://www.seeedstudio.com/wiki/Grove_-_Base_Shield_V1.3)

- [Ether Shield](http://arduino.cc/en/Main/ArduinoEthernetShield)

**OR**

- [Arduino Ethernet](http://arduino.cc/en/Main/ArduinoBoardEthernet)

- [Stacking headers](http://www.adafruit.com/products/85)

- [Grove Shield](http://www.seeedstudio.com/wiki/Grove_-_Base_Shield_V1.3)

**OR**

- [EtherMega](http://www.freetronics.com/products/ethermega-arduino-mega-2560-compatible-with-onboard-ethernet)

- [Stacking headers](http://www.adafruit.com/products/85)

- [Grove Shield](http://www.seeedstudio.com/wiki/Grove_-_Base_Shield_V1.2)

**AND** these sensors:

- [A0 - MD550 Wind Sensor](http://moderndevice.com/product/wind-sensor/)

- [D8 - Grove Dust Sensor](http://www.seeedstudio.com/wiki/Grove_-_Dust_Sensor)

- [A2 - Grove DHT Sensor](http://www.seeedstudio.com/wiki/Grove_-_Temperature_and_Humidity_Sensor_Pro)

Also, import this
[library](http://www.seeedstudio.com/wiki/images/archive/4/49/20130305092204%21Humidity_Temperature_Sensor.zip)
into Arduino.

You **may* need to power the Arudino via mains, not USB --
depending on the Arduino,
the ethernet/sensor draw may be more than a USB-powered Arduino can deliver!

Note that when the MD550 sensor starts,
it takes 50 seconds before returning control back to `setup()`.

A report via the TSRP looks like the following.
Note that the `flow` property is defined as 'epsilon',
which means that the sensor is reporting uncalibrated data,
and `node-sensor-pod` will report the current value relative to the standard deviation of the data series.

        {
          "path": "/api/v1/thing/reporting",
          "requestID": "1",
          "things": {
            "/device/climate/arduino/ventilation": {
              "prototype": {
                "device": {
                  "name": "Return Ventilation Sensor Array",
                  "maker": "Modern Device/Seed Studio"
                },
                "name": "true",
                "status": [
                  "present",
                  "absent",
                  "recent"
                ],
                "properties": {
                  "flow": "epsilon",
                  "particulates": "pcs/liter",
                  "temperature": "celcius",
                  "humidity": "percentage"
                }
              },
              "instances": [
                {
                  "name": "Return Ventilation Sensor",
                  "status": "present",
                  "unit": {
                    "serial": "deadbeefff06",
                    "udn": "195a42b0-ef6b-11e2-99d0-deadbeefff06-ventilation"
                  },
                  "info": {
                    "flow": 1.0452,
                    "particulates": 1346.2656,
                    "temperature": 24.5,
                    "humidity": 32.1
                  },
                  "uptime": 82576
                }
              ]
            }
          }
        }
