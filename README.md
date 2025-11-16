# ESP32-CAM Multi-Client Video Streamer

A lightweight and efficient **ESP32-CAM video streaming server** that streams live video over **Wi-Fi** to **multiple clients simultaneously**.  
Supports MJPEG/HTTP streaming, low latency, and works with any web browser, VLC, or custom applications.  
Perfect for IoT, surveillance, robotics, and remote monitoring.

---

## 🚀 Features

- 📷 **Live MJPEG/HTTP video streaming**
- 👥 **Multi-client support** (multiple viewers at the same time)
- ⚡ **Low latency** and optimized frame handling
- 🌐 Works on **Wi-Fi STA/AP mode**
- 🧩 Compatible with **ESP32-CAM (AI Thinker)** and similar modules
- 🎛 **Configurable**: resolution, quality, Wi-Fi credentials
- 🛠 Built using **Arduino framework**

---

## 📦 Requirements

- ESP32-CAM (AI Thinker) or compatible module  
- FTDI / USB-TTL programmer  
- Arduino IDE (or PlatformIO)  
- ESP32 board package installed  

---

## 🔧 Installation & Setup

1. Install **ESP32 board support** in Arduino IDE  
   - *File → Preferences → Additional Boards URL:*  
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```

2. Select the board:  
   **Tools → Board → ESP32 Arduino → AI Thinker ESP32-CAM**

3. Add the required libraries (if any are used in your code).

4. Flash the code using:
   - Baud rate: **115200**
   - Flash mode: **QIO**
   - Partition scheme: **Huge App** (if streaming code is large)

5. Open **Serial Monitor** to get the device's IP address.

---

## 🌐 Usage

1. Power the ESP32-CAM after flashing  
2. Open Serial Monitor to find:
3. WiFi connected!
Stream URL: http://<your-ip>:<port>/

3. Open the provided URL in:
- Chrome / Firefox / Edge  
- VLC Media Player  
- Any MJPEG-compatible viewer  

---

## 📺 Stream Access

Typical URLs (depending on your code):

- **Main stream:**  


http://<ip-address>/stream


- **Single frame snapshot:**  


http://<ip-address>/capture


- **Control endpoints (if implemented):**  
- `/start`
- `/stop`
- `/resolution`
- `/quality`  

---

## 🛠 Configuration

You can adjust settings in the source code:

- **Wi-Fi SSID & Password**  
- **Camera resolution** (UXGA → QQVGA)  
- **JPEG quality**  
- **Port number**  
- **Frame buffer count**  

Example:

```cpp
config.frame_size = FRAMESIZE_QVGA;
config.jpeg_quality = 10;
