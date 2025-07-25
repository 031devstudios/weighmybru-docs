# Serial Monitor

# 🛠️ Using VSCode Toolbar to View ESP32 Serial Output

This guide explains how to use **Visual Studio Code (VSCode)** and the **PlatformIO extension** to monitor serial debug output from your ESP32 using the **bottom toolbar**—no terminal commands required.

---

## 📥 Prerequisites

Make sure you have the following installed:

- [Visual Studio Code](https://code.visualstudio.com/)
- [PlatformIO IDE extension](https://platformio.org/install/ide?install=vscode)
- Correct USB driver for your ESP32 board (e.g. CP210x, CH340, FTDI)

---

## 🔌 Step 1: Connect Your ESP32

1. Plug your ESP32 board into your computer using a USB data cable.
2. You should see a small LED light up on the board.

---

## 📁 Step 2: Open Your PlatformIO Project

1. Open VSCode.
2. Open your PlatformIO project folder.
3. Wait for the PlatformIO toolbar (bottom blue bar) to appear.

---

## 🧭 Step 3: Select the Serial Port

1. In the bottom toolbar, find the section that shows the current **serial port** (e.g. `COM4`, `/dev/ttyUSB0`, or `Not selected`).
2. Click on it.

   <img src="media/troubleshooting/com-port.png" alt="WebUI-AP" width="80" height="30">

3. A dropdown will appear showing available ports.
4. Choose the one that matches your ESP32 (the port usually appears after you plug in the board).

---

## 🖥️ Step 4: Open the Serial Monitor

1. Click the **"Plug" icon** in the bottom toolbar.

   <img src="media/troubleshooting/serial-monitor.png" alt="WebUI-AP" width="30" height="30">

2. The **Serial Monitor** will open in the Terminal pane.
3. You should start seeing output like this:

   ```plaintext
   SSD1306 display initialized on SDA:5 SCL:6
Display initialized - ready for messages
Wakeup was not caused by deep sleep: 0
WiFi: OK in 1ms
AP IP: 192.168.4.1
.....
Connected to STA with IP: 192.168.1.59
mDNS responder started
Access the scale at: http://weighmybru.local
BluetoothScale: Started advertising as WeighMyBru
Digital touch sensor initialized on pin 4
Power Manager initialized. Sleep touch sensor on GPIO3
Using EXT0 wake-up (digital touch sensor)
Device will wake up when touch sensor outputs HIGH
=== EEPROM Performance Diagnostics ===
EEPROM test write/read took: 1 ms
WiFi namespace read took: 0 ms
Display namespace read took: 0 ms
=== End Diagnostics ===
Pre-caching settings for faster page loads...
Display: OK in 0ms
