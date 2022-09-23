# ESP32 home ambient monitor.

## Hardware

### ESP32 wroom

This is a device we are going to place the logic of the project and to report in our reporting infrastructure (HTTP POST or MQQT) the readings of the sensor temperature and humidity.


### ESP32 Pinout

One popular ESP32 Development Board available today is the 30-pin version shown in the above image. It consists of ESP-WROOM-32 as the baseboard and additionally few pins and components to easily interact with ESP32.

The following image shows the pinout of a 30-pin ESP32 DevKit Development Board.

![ESP32 Pinout](/img/ESP32-Pinout-1.jpg)

### Temperature and humididty Sensor

We are going to use [DHT11](https://components101.com/sensors/dht11-temperature-sensor) Temperature and Humidity Sensor module or similar with three pinouts

- Vcc - Power supply 3.5V to 5.5V
- Data - Outputs both Temperature and Humidity through serial Data
- Ground - Connected to the ground of the circuit

This is a simple sensor you can get online very cheap

![DHT11 Sensor](img/DHT11%E2%80%93Temperature-Sensor-Pinout.jpg)

### Assembly
We can connect together the ESP32 and the rest of the devices on a bradboard. Connection schematics belo

TODO




## Software

We are going to use Arduino studio to build the software layer for this project. In a high level overview the software logic would have to achieve the following

- Connect to a wireless network. Initially would be hardcoded SSID but a feature can be added to allow a selection of the AP while the ESP32 device is starting up
- Read the tempoerature and humidity from the DHT11 (or any other) sensor
- Post this data on a message broker or a HTTP POST for long term retention.
- (Optional) build a graph for example with Grafana to visualize the historical data.

