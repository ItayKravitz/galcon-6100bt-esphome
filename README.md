# galcon-6100bt-esphome

An open-source ESPHome configuration for integrating Galcon 6100BT (and compatible BLE irrigation controllers) with Home Assistant via an ESP32 Gateway.

Instead of replacing a reliable Galcon controller with an expensive smart alternative, I reverse-engineered its BLE protocol. Using a low-cost ESP32 running ESPHome, this project acts as a local Bluetooth proxy, bringing full multi-valve control and status tracking seamlessly into Home Assistant.

## Features

  Multi-Valve Control: Full ON/OFF control for up to 6 irrigation valves with connection retry logic.
  Real-time Status Tracking: Binary sensors reflecting real-time valve state using bitmask decoding.
  Active Valve & Timer Sensors: Live indicators for which valve is currently running and remaining irrigation time.
  BLE RSSI & Connection Monitoring: Track signal strength and connection status between ESP32 and Galcon.

## Prerequisites

Hardware:
  ESP32 Development Board.
  Galcon 6100BT Irrigation Controller within Bluetooth range of the ESP32.
Software:
  Home Assistant with ESPHome Add-on installed.
  Known MAC address of your Galcon controller (obtainable via nRF Connect app or ESP32 BLE scanner).

## Quick Start & Installation

1. Clone or copy the `galcon-6100bt.yaml` configuration into your ESPHome directory.
2. Create a `secrets.yaml` file (or add to your existing secrets) with your network parameters:
   ```yaml
   wifi_ssid: "Your_WiFi_SSID"
   wifi_password: "Your_WiFi_Password"
