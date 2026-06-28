# Robonavigators Tools

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Welcome to the official deployment hub for Robonavigators hardware. This repository hosts web-based tools for managing, monitoring, and flashing your ESP32-based devices directly from your browser.

**Access the dashboard here:** [Robonavigators Tools](https://robonavigators.github.io)

---

## Available Tools

### 1. Web Serial Flasher
A browser-based tool to flash pre-compiled firmware or your own custom `.bin` files directly to your board over USB.
* **Technology:** Web Serial API
* **Supported Devices:** ESP8266, ESP32, ESP32-S2/S3, ESP32-C2/C3/C5/C6, ESP32-H2, ESP32-P4.

### 2. Erase Flash Memory
A utility tool to completely wipe the flash memory of your board.
* **Purpose:** Clearing corrupted partitions, removing stored Wi-Fi credentials, or performing a complete factory reset.
* **Technology:** Web Serial API (ROM Bootloader)

### 3. Serial Monitor
A real-time terminal interface to view console logs and interact with your device.
* **Function:** Debugging, monitoring sensor data, and sending terminal commands via USB.

### 4. OTA Wireless Uploader
A web-based interface to push firmware updates to your devices over Wi-Fi.
* **Requirements:** Device must be on the same network as your computer and running firmware with an active OTA WebServer.

---

## How to use

### Web Serial Flashing
1. Connect your ESP32 board to your computer via USB.
2. Navigate to the **[ESP Flasher](https://robonavigators.github.io/flash.html)**.
3. Select the desired project or click "Add your own .bin".
4. Click **Connect** and follow the browser prompts to select your port.

### Erase Flash Memory
1. Connect your ESP32 board to your computer via USB.
2. Navigate to the **[Erase Flash](https://robonavigators.github.io/erase_flash.html)** tool.
3. Click **Connect & Erase** and confirm the port selection.
4. Note: This will render the board unbootable until new firmware is flashed.

### Serial Monitoring
1. Navigate to the **[Serial Monitor](https://robonavigators.github.io/serial_monitor.html)**.
2. Select your baud rate and click **Connect**.

### Wireless OTA Updates
1. Navigate to the **[OTA Uploader](https://robonavigators.github.io/ota.html)**.
2. Enter the device IP address and upload your `.bin` file.

---

## Technical Architecture

The following diagram illustrates how these browser-based tools interact with your hardware:



---

## Technical Notes

### Custom Binaries
* **For Web Serial Flashing:** The tool dynamically generates a manifest that targets all common Espressif chip families to ensure maximum compatibility.

### Troubleshooting
* **Connection Issues:** Ensure you are using a data-capable USB cable.
* **Permissions:** If the browser cannot see your board, ensure no other programs (e.g., Arduino IDE, Serial Monitor) are currently using the serial port.
* **Network:** For OTA updates, verify your device IP and ensure your computer is not on a "Guest" network that isolates Wi-Fi clients.

*Built for the community, by Robonavigators.*
*Use at your own risk.*
