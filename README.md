# Robonavigators Tools

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Welcome to the official deployment hub for Robonavigators hardware. This repository hosts web-based tools for flashing and updating your ESP32-based devices directly from your browser.

**Access the dashboard here:** [Robonavigators Tools](https://robonavigators.github.io)

## Available Tools

### 1. Web Serial Flasher
A browser-based tool to flash pre-compiled firmware or your own custom `.bin` files directly to your board over USB.
* **Technology:** Web Serial API
* **Supported Devices:** ESP8266, ESP32, ESP32-S2/S3, ESP32-C2/C3/C6, ESP32-H2, ESP32-P4.

### 2. OTA Wireless Uploader
A web-based interface to push firmware updates to your devices over Wi-Fi.
* **Requirements:** Device must be on the same network as your computer and running firmware with an active OTA WebServer.
* **Method:** HTTP POST via `/update` route.

---

## How to use

### Web Serial Flashing
1. Connect your ESP32 board to your computer via USB.
2. Navigate to the **[ESP Flasher](https://robonavigators.github.io/flash.html)**.
3. Select the desired project or click "Add your own .bin".
4. Click **Connect** and follow the browser prompts to select your port.

### Wireless OTA Updates
1. Ensure your board is connected to your local Wi-Fi.
2. Find the local IP address of your device (e.g., `192.168.1.50`).
3. Navigate to the **[OTA Uploader](https://robonavigators.github.io/ota.html)**.
4. Enter the device IP address and upload your `.bin` file.

---

## Technical Architecture

The following diagram illustrates how the tools interact with your hardware:



---

## Technical Notes

### Custom Binaries
* **For Web Serial Flashing:** The tool dynamically generates a manifest that targets all common Espressif chip families to ensure maximum compatibility.
* **For OTA Updates:** Ensure your device firmware has the `ArduinoOTA` or `AsyncOTA` library initialized with the `/update` endpoint enabled.

### Troubleshooting
* **Connection Issues:** Ensure you are using a data-capable USB cable.
* **Permissions:** If the browser cannot see your board, ensure no other programs are currently using the serial port.
* **Network:** For OTA updates, if the upload fails, verify the device's IP address and ensure your computer is not on a "Guest" network that isolates Wi-Fi clients.


*Built for the community, by Robonavigators.*

