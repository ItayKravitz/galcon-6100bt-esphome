# galcon-6100bt-esphome

An open-source ESPHome configuration for integrating Galcon 6100BT (and compatible BLE irrigation controllers) with Home Assistant via an ESP32 Gateway.

## Project Background

Instead of replacing a reliable Galcon controller with an expensive smart alternative, I reverse-engineered its BLE protocol. Using a low-cost ESP32 running ESPHome, this project acts as a local Bluetooth proxy, bringing full multi-valve control and status tracking seamlessly into Home Assistant.

## Features

- **Multi-Valve Control:** Full ON/OFF control for up to 6 irrigation valves with connection retry logic.
- **Real-Time Status Tracking:** Binary sensors reflecting real-time valve state using bitmask decoding.
- **Active Valve & Timer Sensors:** Live indicators for which valve is currently running and remaining irrigation time.
- **BLE RSSI & Connection Monitoring:** Track signal strength and connection status between ESP32 and Galcon.

## Prerequisites

**Hardware:**
- ESP32 Development Board.
- Galcon 6100BT Irrigation Controller within Bluetooth range of the ESP32.

**Software:**
- Home Assistant with ESPHome Add-on installed.
- Known MAC address of your Galcon controller (obtainable via nRF Connect app or ESP32 BLE scanner).

## Quick Start & Installation

1. Copy or clone the configuration file into your ESPHome directory.
2. Create or update your `secrets.yaml` with your Wi-Fi credentials.
3. Update the MAC address in the YAML configuration file to match your controller.
4. Compile and flash the code to your ESP32.
