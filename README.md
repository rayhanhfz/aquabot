# 🌊 Aquabot ESP8266 – Smart Water Tank Monitoring with Blynk

Aquabot is an IoT project built using **ESP8266**, **ultrasonic water level sensor**, **relay-controlled pump**, and **servo motor** to monitor and control a water tank automatically. The system is connected to the **Blynk IoT platform**, providing real-time data and control via mobile app.

## 🚀 Features

- 📡 **Real-time water level monitoring** using ultrasonic sensor
- ⚙️ **Automatic & manual pump control** based on tank level
- 🔄 **Servo motor control** from Blynk (e.g., valve or lid)
- 📲 **Blynk dashboard integration** (virtual pins V0–V5)
- 🔧 Built with **PlatformIO** and supports **GitHub Actions CI**

---

## 🧩 Hardware Required

- 1x ESP8266 NodeMCU
- 1x HC-SR04 Ultrasonic Sensor
- 1x 5V Relay Module
- 1x Mini Water Pump
- 1x Servo Motor (e.g., SG90)
- Jumper wires & Breadboard
- Power Supply (5V USB or adapter)

---

## 📱 Blynk Virtual Pin Mapping

| Function             | Blynk Virtual Pin |
| -------------------- | ----------------- |
| Distance (raw)       | V0                |
| Water height (cm)    | V1                |
| Water level (%)      | V4                |
| Pump status (text)   | V2                |
| Pump manual switch   | V3                |
| Servo angle (slider) | V5                |

---

## ⚙️ PlatformIO Setup

**`platformio.ini`** config:

```ini
[env:nodemcuv2]
platform = espressif8266
board = nodemcuv2
framework = arduino
lib_deps =
  blynkkk/Blynk
  paulstoffregen/NewPing
```

---

## 🛠️ How to Flash

1. Install [VS Code](https://code.visualstudio.com/) + [PlatformIO](https://platformio.org/install)
2. Clone this repo:

```bash
git clone https://github.com/reyhanhfz/aquabot.git
cd aquabot
```

3. Rename and edit `include/secrets.h`:

```cpp
#define BLYNK_TEMPLATE_ID "TMPLxxxx"
#define BLYNK_TEMPLATE_NAME "aquabot"
#define BLYNK_AUTH_TOKEN "your_auth_token"
#define WIFI_SSID "your_wifi"
#define WIFI_PASS "your_password"
```

4. Plug in your ESP8266
5. Build & Upload via PlatformIO (or `pio run --target upload`)

---

## 🧠 Project Diagram (Wiring)

- **HC-SR04**
  - TRIG → D2
  - ECHO → D1
- **Relay** → D5
- **Servo** → D7
- **GND** semua disambungkan ke GND
- **VCC** ke 5V (via breadboard)

> Note: Use voltage divider or logic level shifter if needed

---

## 🧪 Future Improvements

- OTA update
- Flood detection
- Battery voltage monitoring
- Notification via Telegram

---

## 👨‍💻 Author

Made with ❤️ by **aquabot developer team**

---

## 📄 License

This project is open-source under the MIT License.
