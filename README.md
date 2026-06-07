# 🦆 Theo's Ducky Converter

A high-performance, Stark-inspired web interface engineered for transforming raw scripts or multi-line source code into hardware-compliant **Duckyscript**. This utility features an advanced layout engine specifically optimized to preserve strict structural indentation across wireless and hardware communication bridges, preventing characters from clipping or misaligning when flashed to customized HID injectors.

---

## ⚡ Hardware Integration Focus: WiFi Ducky Architecture

When dealing with a dual-chip setup like the **WeMos D1 Mini (ESP8266)** linked with an **ATmega32U4 (Arduino Pro Micro)**, commands cross from a local websocket terminal server over to hardware serial registers (`TX/RX`). This layout profile actively protects your code streams against the common bottlenecks found in **Spacehuhn WiFi Ducky firmware** and **custom serial passthrough profiles**:

* **Serial Buffer Overflow Protection:** Automatically configured to introduce a **150ms** baseline loop pacing delay. This provides the ESP8266 serial pipeline with necessary runtime buffering margins to fully pass data packets over UART before the ATmega maps them out as native USB keyboard scans, preventing character drops.
* **Microcontroller Trim Bypass:** Spacehuhn and custom passthrough firmware profiles routinely drop or misread leading spaces when handling a combined string block to maximize volatile heap space. Enabling the **Hardware Indentation Protection Block** explicitly breaks spaced logic loops away from text contents:
  ```duckyscript
  STRING      
  STRING print("System Stable")
