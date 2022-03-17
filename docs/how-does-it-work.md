Communication

These section describes the communication process between the [ESP32WifiConfigurator.h](esp32-wifi-configurator.md) library and the [WiFi Configurator](wifi-esp32-configurator-app.md) application.

## Connection Setup

The ESP32 controller uses the [ESP32WifiConfigurator.h](esp32-wifi-configurator.md) library in his `setup()` method to check, whether the microcontroller is connected to a WiFi network. When no WiFi conncetion is present it setups a BLE Server. This server advertises a BLE Service, which the [WiFi Configurator](wifi-esp32-configurator-app.md) application is scanning for. The application can establish a BLE conncetion to the found Device (ESP32).

## Read available WiFi netwrok SSIDs

The [ESP32WifiConfigurator.h](esp32-wifi-configurator.md) library also scans for available nearby WiFi networks and publishes the names (SSIDs) via BLE Characteristics of the advertised BLE Service.

![](./resources/wifi_names.png)

## Set WiFi Credentials 
[WiFi Configurator](wifi-esp32-configurator-app.md) application shows the available networks to the user. The user can then choose a network from the list and submit the according password to the connected BLE device.

![](./resources/set_password.png)

## Shutdown choreographie
To close the connection for both sides in a controlled way two messages are exchanged between the microcontroller and the application.

1. On a successfull established WiFi connection the message "SUCCESS" is writen to the *Available Networks Communication Characteristics* by the microcontroller
2. On Reading the "SUCCESS" message the application writes the message "CLOSED" to the same characteristics and disconnects from the BLE connection.
3. On Reading the "CLOSED" message the microcontroller shuts down the BLE server closing all BLE connections.

![](./resources/shutdown.png)

## Image Resources

<a href="https://www.flaticon.com/free-icons/bluetooth" title="bluetooth icons">Bluetooth icon created by Freepik - Flaticon</a>

<a href="https://www.flaticon.com/free-icons/microcontroller" title="microcontroller icons">Microcontroller icon created by Eucalyp - Flaticon</a>

<a href="https://www.flaticon.com/free-icons/smartphone" title="smartphone icons">Smartphone icon created by Good Ware - Flaticon</a>

<!-- <a href="https://www.flaticon.com/free-icons/wifi" title="wifi icons">Wifi icons created by Freepik - Flaticon</a>

<a href="https://www.flaticon.com/free-icons/bluetooth" title="bluetooth icons">Bluetooth icons created by Freepik - Flaticon</a>

<a href="https://www.flaticon.com/free-icons/bluetooth" title="bluetooth icons">Bluetooth icons created by Smashicons - Flaticon</a> -->



