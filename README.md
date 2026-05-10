# Introduce 

A radiofrequency intervention device helps you understand and grasp the different frequency ranges and how each technique works.

# Multi-Protocol RF & NFC Research Tool (ESP32-Based)

A comprehensive hardware platform designed for radio frequency (RF) exploration, signal analysis, and security auditing. This project integrates Sub-GHz, 2.4GHz, and NFC/RFID capabilities into a single handheld unit powered by the **ESP32-2432S028** (Cheap Yellow Display).

## 🛠 Hardware Architecture

* **MCU & Display:** ESP32-2432S028 (2.8" TFT Touchscreen + ESP32-WROOM-32).
* **Sub-GHz RF:** CC1101 Module (Supporting 300MHz - 928MHz).
* **2.4GHz RF:** nRF24L01+ PA+LNA (High-range 2.4GHz transceiver).
* **NFC/RFID:** PN532 Module (13.56MHz contactless communication).
* **Connectivity:** SPI Bus sharing with custom DIP Switch logic for module isolation.

---

## 📡 How It Works

### 1. ESP32-2432S028 (Central Controller)
The core of the device. It handles the User Interface (UI) via the touchscreen and manages data traffic between all peripheral modules. It uses the SPI bus to talk to the CC1101 and nRF24L01, and I2C/SPI for the PN532.

### 2. CC1101 (Sub-GHz Transceiver)
* **Frequency Range:** 300MHz to 928MHz.
* **Operation:** This module specializes in digital modulation like OOK, ASK, and FSK. It is used to "sniff" or capture radio signals from common wireless devices (garage doors, weather stations, or smart home sensors). Once captured, these signals can be analyzed or replayed for security testing.

### 3. nRF24L01+ (2.4GHz Wireless)
* **Frequency Range:** 2.4GHz ISM Band.
* **Operation:** Utilizing Gaussian Frequency Shift Keying (GFSK), this module is primarily used for high-speed wireless data. In this tool, it serves to monitor 2.4GHz traffic, perform spectrum scanning to identify interference, or test the security of wireless HID devices (keyboards/mice).

### 4. PN532 (NFC/RFID)
* **Frequency:** 13.56MHz.
* **Operation:** It works through electromagnetic induction. The module acts as an initiator, creating an RF field that powers passive tags. It can read/write data, emulate cards, and interact with NFC-enabled smartphones or transit cards.

---

## 🔧 Installation & Wiring

The project uses a shared SPI bus. To prevent data collisions, a **DIP Switch system** is implemented to manually enable/disable the Chip Select (CS) and power lines for specific modules.

> [!IMPORTANT]  
> Refer to the `wiring-diagram.png` in the repository for the exact pinout and SPI configurations.

---

## ⚠️ Ethical Disclosure & Disclaimer

This tool is intended for **educational purposes and authorized security research only**. 
* Always comply with your local telecommunications laws and regulations.
* The developer (Kendrick) assumes no liability for misuse or damage caused by this device.

---
*Created and maintained by Kendrick.*
