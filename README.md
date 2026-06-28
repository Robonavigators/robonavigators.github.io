# Robonavigators Tools

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Welcome to the official deployment hub for Robonavigators hardware. This repository hosts web-based tools for managing, monitoring, and flashing your ESP32-based devices directly from your browser.

**Access the dashboard here:** [Robonavigators Tools](https://robonavigators.github.io)

---

## Available Tools

### 1. Web Serial Flasher
A browser-based tool to flash pre-compiled firmware or your own custom `.bin` files directly to your board over USB.
* **Technology:** Web Serial API
* **Supported Devices:** ESP8266, ESP32, ESP32-S2/S3, ESP32-C2/C3/C6, ESP32-H2, ESP32-P4.

### 2. Serial Monitor
A real-time terminal interface to view console logs and interact with your device.
* **Function:** Debugging, monitoring sensor data, and sending terminal commands via USB.
* **Features:** Variable baud rate support and direct serial input/output.

### 3. OTA Wireless Uploader
A web-based interface to push firmware updates to your devices over Wi-Fi.
* **Requirements:** Device must be on the same network as your computer and running firmware with an active OTA WebServer.
* **Method:** HTTP POST via `/update` route.

### 4. Erase Flash Memory
A utility tool to completely wipe the flash memory of your board.
* **Purpose:** Clearing corrupted partitions, removing stored Wi-Fi credentials, or performing a factory reset.

---

## How to use

### Web Serial Flashing & Erasing
1. Connect your ESP32 board to your computer via USB.
2. Navigate to the **[ESP Flasher](https://robonavigators.github.io/flash.html)** or **[Erase Flash](https://robonavigators.github.io/erase_flash.html)** tool.
3. Click **Connect** and follow the browser prompts to select your serial port.
4. For flashing: select a project or click "Add your own .bin".

### Serial Monitoring
1. Navigate to the **[Serial Monitor](https://robonavigators.github.io/serial_monitor.html)**.
2. Select your desired baud rate (default: 115200).
3. Click **Connect** and power cycle your board to view boot logs.

### Wireless OTA Updates
1. Ensure your board is connected to your local Wi-Fi.
2. Navigate to the **[OTA Uploader](https://robonavigators.github.io/ota.html)**.
3. Enter the device IP address and upload your `.bin` file.

---

## Technical Architecture

The following diagram illustrates how these browser-based tools interact with your hardware:



---

## Technical Notes

### Custom Binaries
* **For Web Serial Flashing:** The tool dynamically generates a manifest that targets all common Espressif chip families to ensure maximum compatibility.

### Troubleshooting
* **Connection Issues:** Ensure you are using a data-capable USB cable (some are power-only).
* **Permissions:** If the browser cannot see your board, ensure no other applications (like Arduino IDE, VS Code, or another browser tab) are currently using the serial port.
* **Network:** For OTA updates, verify the device's IP address and ensure your computer is not on a "Guest" network that isolates Wi-Fi clients.

*Built for the community, by Robonavigators.*
*Use at your own risk.*
