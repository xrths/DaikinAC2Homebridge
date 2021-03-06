<!-- PROJECT SHIELDS -->

[![Arduino](https://img.shields.io/badge/Made%20with-Arduino-blue?style=for-the-badge&logo=Arduino)](https://www.arduino.cc/)
[![Homebridge](https://img.shields.io/badge/Work%20with-Homebridge-orange?style=for-the-badge&logo=Homebridge)](https://homebridge.io/)

# DaikinAC2Homebridge
Control your Daikin AC with Homebridge (MQTT) using an ESP8266 and an IR led.

## Based on : 
<a href="https://github.com/sisimomo/ESP8266-Daikin-ARC-BRC-Controller">NodeMCU ESP8266 - Daikin ARC/BRC Controller</a>

## Homebridge configuration

* Install the "homebridge-mqttthing" plugin
* Configure the plugin like this:
```
    "accessories": [
        {
            "type": "heaterCooler",
            "name": "Clim",
            "username": "user",
            "password": "password",
            "optimizePublishing": true,
            "topics": {
                "getActive": "DaikinAC2Homebridge/Power",
                "setActive": "DaikinAC2Homebridge/Power",
                "getCoolingThresholdTemperature": "DaikinAC2Homebridge/Temperature",
                "setCoolingThresholdTemperature": "DaikinAC2Homebridge/Temperature",
                "getCurrentHeaterCoolerState": "DaikinAC2Homebridge/Mode",
                "getCurrentTemperature": "DaikinAC2Homebridge/Temperature",
                "getHeatingThresholdTemperature": "DaikinAC2Homebridge/Temperature",
                "setHeatingThresholdTemperature": "DaikinAC2Homebridge/Temperature",
                "getRotationSpeed": "DaikinAC2Homebridge/FanSpeed",
                "setRotationSpeed": "DaikinAC2Homebridge/FanSpeed",
                "getSwingMode": "DaikinAC2Homebridge/Swing",
                "setSwingMode": "DaikinAC2Homebridge/Swing",
                "getTargetHeaterCoolerState": "DaikinAC2Homebridge/Mode",
                "setTargetHeaterCoolerState": "DaikinAC2Homebridge/Mode"
            },
            "minTemperature": 20,
            "maxTemperature": 27,
            "accessory": "mqttthing"
        }
    ],
```

## Wiring Diagram

![Wiring Diagram](Wiring%20Diagram.png)

### Parts

* NodeMCU ESP8266 - Qty: 1
* LED - Basic Green 5mm - Qty: 1
* 100 Ohm Resistor - Qty: 1
* Infrared (IR) LED 950nm - Qty: 1
* Transistor - NPN BC337 - Qty: 1
* 220 Ohm Resistor - Qty: 1
* Mini Pushbutton Switch - Qty: 1
* 10K Ohm Resistor - Qty: 1

## Compatibility
### Compatible with AC:
```
* FTK09NMVJU
* FTX09NMVJU
* FTK12NMVJU
* FTX12NMVJU (Tested with)
* FTK18NMVJU
* FTX18NMVJU
* FTK24NMVJU
* FTX24NMVJU
* AND A LOT MORE
```

### Compatible with AC remote:

#### If the remote used for your Daikin AC remote Start With ARC or BRC, it should be compatible.

```
* ARC480A1  * ARC480A11 * ARC480A21 * ARC480A31
* ARC480A2  * ARC480A12 * ARC480A22 * ARC480A32
* ARC480A3  * ARC480A13 * ARC480A23 * ARC480A33
* ARC480A4  * ARC480A14 * ARC480A24 * ARC480A34
* ARC480A5  * ARC480A15 * ARC480A25 * ARC480A35
* ARC480A6  * ARC480A16 * ARC480A26 * ARC480A36
* ARC480A7  * ARC480A17 * ARC480A27 * ARC480A37
* ARC480A8  * ARC480A18 * ARC480A28
* ARC480A9  * ARC480A19 * ARC480A29
* ARC480A10 * ARC480A20 * ARC480A30
* BRC073a4 * BRC073a5 * BRC073a7 * BRC1E62
* BRC4C155 * BRC4C158 * BRC4C152 * BRC1C62
* BRC7F634F * BRC7F635F
* AND A LOT MORE
```

## Big thanks to

* [sisimomo](https://github.com/sisimomo) For the code base of [ESP8266-Daikin-ARC-BRC-Controller](https://github.com/sisimomo/ESP8266-Daikin-ARC-BRC-Controller)
* [tzapu](https://github.com/tzapu) For is Amazing librarie [WiFiManager](https://github.com/tzapu/WiFiManager)
* [knolleary](https://github.com/knolleary) For is Amazing librarie [PubSubClient](https://github.com/knolleary/pubsubclient)
* [danny-source](https://github.com/danny-source) For is Amazing librarie [Arduino_DY_IRDaikin ARC/BRC](https://github.com/danny-source/Arduino_DY_IRDaikin)
* [bblanchon](https://github.com/bblanchon) For is Amazing librarie [ArduinoJson](https://github.com/bblanchon/ArduinoJson)