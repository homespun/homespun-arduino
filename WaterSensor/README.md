# Arduino + Grove Shield + Grove Water Sensor

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

**AND** this sensor:

- [D7 - Grove Water Sensor](http://www.seeedstudio.com/wiki/Grove_-_Water_Sensor)


A report via the TSRP looks like the following:

        {
          "path": "/api/v1/thing/reporting",
          "requestID": "1",
          "things": {
            "/device/sensor/grove/water": {
              "prototype": {
                "device": {
                  "name": "Grove Water Sensor",
                  "maker": "Seeed Studio"
                },
                "name": "true",
                "status": [
                  "present",
                  "absent",
                  "recent"
                ],
                "properties": {
                  "liquid_detected": "boolean"
                }
              },
              "instances": [
                {
                  "name": "Water Sensor",
                  "status": "present",
                  "unit": {
                    "serial": "deadbeefff04",
                    "udn": "195a42b0-ef6b-11e2-99d0-deadbeefff04-water"
                  },
                  "info": {
                    "liquid_detected": false
                  },
                  "uptime": 60512
                }
              ]
            }
          }
        }
