Kaa application based on Raspberry Pi and DHT11 sensor
============================
This sample RaspberryPI application collects temperature measurements from DHT11 sensor and uploads it to Cassandra using Kaa.

Kaa is an open-source middleware platform for building, managing, and integrating connected products with the Internet of Everything.

Installation instruction

* Get [Rasberry Pi 2 Model B](https://en.wikipedia.org/wiki/Raspberry_Pi), [DHT 11 sensor](http://www.dx.com/p/arduino-digital-temperature-humidity-sensor-module-121350#.Vea7HHWlxBc) and 3 Male-Male jumper wires.
* Install third-party components for C SDK using this [steps](http://docs.kaaproject.org/display/KAA/Raspberry+Pi#RaspberryPi-Installingthird-partycomponentsforCSDK).
* [Raspberry Pi] Install the [WiringPi](http://wiringpi.com/) library.
```
git clone git://git.drogon.net/wiringPi
cd wiringPi
./build
```
* [Raspberry Pi] Clone the repository of the Kaa Cassandra sample.
```
git clone https://github.com/kaaproject/kaa-cassandra-sample.git
```
* [Raspberry Pi] Generate the Kaa C SDK ant put it to the [kaa-cassandra-sample/client/c/libs/kaa](https://github.com/kaaproject/kaa-cassandra-sample/tree/master/client/c/libs/kaa) directory.
* Connect wires using following schema.
  - Connect DHT11 pin 1 (left) to Raspberry PI pin 7 (GPIO 4)
  - Connect DHT11 pin 2 (middle) to Raspberry PI pin 1 (VCC)
  - Connect DHT11 pin 3 (right) to Raspberry PI pin 14 (GND)
  
  ![DHT11](https://github.com/kaaproject/kaa-cassandra-sample/blob/master/schema.jpg)
  * [Raspberry Pi] Build the client demo based on the Kaa C SDK.
  ```
  cd kaa-cassandra-sample/client/c
  ./build.sh deploy
  ```
  * [Raspberry Pi] Observe console output.
  ```
  Data collection demo started
  Going to add 1th log record: { id: 'Sensor 1', region: 'Region 1', model: 'DHT11', val: 25 }
  Going to add 2th log record: { id: 'Sensor 1', region: 'Region 1', model: 'DHT11', val: 25 }
  Going to add 3th log record: { id: 'Sensor 1', region: 'Region 1', model: 'DHT11', val: 25 }
  Going to add 4th log record: { id: 'Sensor 1', region: 'Region 1', model: 'DHT11', val: 25 }
  Going to add 5th log record: { id: 'Sensor 1', region: 'Region 1', model: 'DHT11', val: 25 }
  ```