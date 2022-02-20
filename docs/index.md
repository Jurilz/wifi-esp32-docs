# Overview

This project is a combination of a ESP32 Libraray ([ESP32WifiConfigurator.h](esp32-wifi-configurator.md)) and a Flutter Mobile Application ([WiFi ESP32 Configurator App](wifi-esp32-configurator-app.md)). It allows to set WiFi credentials for an ESP32 controller via a BLE connection.

## Repositories

The projet consists of the following repositories:

### ESP32 Wifi Configurator Library
The [ESP32 Wifi Configurator Library Repository](https://github.com/Jurilz/esp32_wifi_lib) contains the ESP32 Library. It enables you to set WiFi credentials for an ESP32 Controller via a BLE conncetion. On start it scans for availble WiFi networks and publishes them via BLE Characteristics. It advertises a BLE Services, which is expected by the [WiFi ESP32 Configurator App](wifi-esp32-configurator-app.md).

### WiFi ESP32 Configurator App
The [WiFi ESP32 Configurator App Repository](https://github.com/Jurilz/wifi-esp32-configurator) contains a cross-plattform Flutter Application which allows to set WiFi credentials on a ESP32 controller via a BLE connection. The [Flutter Blue](https://pub.dev/packages/flutter_blue) Plugin is used for BLE communication.

### Documentation

The [Documentation Repository](https://github.com/Jurilz/wifi-esp32-docs) contains the documents for this documentaiton.