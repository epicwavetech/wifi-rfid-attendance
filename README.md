# 📡 ESP8266 RFID Attendance System

A **Wi-Fi enabled RFID attendance system** built using **ESP8266**, **MFRC522 RFID reader**, and a **16×2 I2C LCD**.  
The system scans RFID cards, sends attendance data securely to a remote server via **HTTPS**, and displays real-time attendance status such as **IN, OUT, LATE, or HALF DAY** on the LCD.

---

## 🚀 Features

- 📶 Wi-Fi connectivity using ESP8266  
- 🔐 RFID card scanning with MFRC522  
- 🌐 Secure HTTPS communication with backend API  
- 🖥 16×2 I2C LCD for real-time user feedback  
- ⏱ Anti-duplicate scan cooldown logic  
- 🆔 Device-based identification for multi-terminal setups  
- 📊 Server-controlled attendance logic (IN / OUT / LATE / HALF DAY)  
- 🔌 Standalone operation (no PC required)

---

## 🧰 Hardware Requirements

| Component        | Description                  |
|------------------|------------------------------|
| ESP8266          | NodeMCU / ESP-12 / ESP-07    |
| RFID Reader      | MFRC522                      |
| Display          | 16×2 I2C LCD                 |
| RFID Tags        | 13.56 MHz cards or key fobs  |
| Power Supply     | 5V / USB                     |
| Jumper Wires     | Male–Female                  |

---

## 🔗 Pin Connections

### RFID (MFRC522 → ESP8266)

| MFRC522 | ESP8266 |
|--------|---------|
| SDA    | D2      |
| SCK    | D5      |
| MOSI  | D7      |
| MISO  | D6      |
| RST   | D1      |
| GND   | GND     |
| 3.3V  | 3.3V    |

### LCD (I2C → ESP8266)

| LCD | ESP8266 |
|-----|---------|
| SDA | D3      |
| SCL | D4      |
| VCC | 5V      |
| GND | GND     |

---

## 📦 Libraries Used

Install the following libraries from **Arduino Library Manager**:

- `ESP8266WiFi`
- `ESP8266HTTPClient`
- `WiFiClientSecure`
- `MFRC522`
- `LiquidCrystal_I2C`
- `SPI`
- `Wire`

---

## ⚙️ Configuration

Update these values in the firmware before uploading:

```cpp
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";

const char* API_URL   = "https://your-domain.com/rfid/attendance.php";
const char* DEVICE_ID = "RFID-01";
