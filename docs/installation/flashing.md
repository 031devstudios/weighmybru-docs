# Flashing

WeighMyBru ESP32 Flash Guide - PlatformIO

## Prerequisites Check
- ✅ VSCode installed
- ✅ PlatformIO extension installed
- ✅ ESP32-S3-WROOM Dev Board
- ✅ USB cable for connection

---

## Step 1: Install Git (if not already installed)

### Windows:
1. Download Git from [git-scm.com](https://git-scm.com/download/win)
2. Run the installer with default settings
3. Open Command Prompt or PowerShell and verify: `git --version`

### macOS:
```bash
# Using Homebrew
brew install git

# Or download from git-scm.com
```

### Linux (Ubuntu/Debian):
```bash
sudo apt update
sudo apt install git
```

---

## Step 2: Clone the WeighMyBru Repository

1. **Open Terminal/Command Prompt**
2. **Navigate to your projects directory:**
   ```bash
   cd ~/Documents  # or wherever you keep projects
   mkdir esp32-projects  # optional: create a projects folder
   cd esp32-projects
   ```

3. **Clone the repository:**
   ```bash
   git clone https://github.com/031devstudios/weighmybru2.git
   cd weighmybru2
   ```

---

---

## Step 3: Open Project in VSCode with PlatformIO

1. **Launch VSCode**
2. **Open the project folder:**
   - File → Open Folder
   - Navigate to and select the `weighmybru` folder you just cloned
   - Click "Select Folder"

3. **Wait for PlatformIO to initialize** (you'll see activity in the bottom status bar)

---

## Step 4: Verify/Configure platformio.ini

Check if the project has a `platformio.ini` file in the root directory. If not, or if you need to modify it for ESP32-S3, create/update it with:

```ini
[env:esp32-s3-devkitc-1]
platform = espressif32@6.12.0
board = esp32-s3-devkitc-1
framework = arduino
monitor_speed = 115200
board_upload.flash_size = 4MB
board_build.filesystem = littlefs
board_build.partitions = huge_app.csv
upload_protocol = esptool
upload_speed = 460800
upload_flags = 
  --chip=esp32s3
  --before=default_reset
  --after=hard_reset
monitor_rts = 0
monitor_dtr = 0
build_flags = 
  -DARDUINO_USB_CDC_ON_BOOT=1
  -DBOARD_HAS_PSRAM
  -Os
  -DCORE_DEBUG_LEVEL=0

lib_deps = 
	robtillaart/HX711@^0.6.0
	https://github.com/me-no-dev/ESPAsyncWebServer.git
	https://github.com/me-no-dev/AsyncTCP.git
	h2zero/NimBLE-Arduino@^1.4.0
	adafruit/Adafruit SSD1306@^2.5.7
	adafruit/Adafruit GFX Library@^1.11.9
```

---

## Step 5: Hardware Connection

1. **Connect your ESP32 to your computer** via USB cable
2. **Put ESP32 in flash mode** (if required):
   - Hold **BOOT** button
   - Press and release **RESET** button
   - Release **BOOT** button
   - *(Some boards auto-reset, so this may not be necessary)*

---

## Step 6: Identify COM Port

### In VSCode with PlatformIO:
1. Look at the bottom blue status bar
2. You should see a COM port listed (e.g., "COM3" on Windows, "/dev/ttyUSB0" on Linux)
3. If not visible, click the PlatformIO icon in the left sidebar → Devices

### Alternatively check manually:
- **Windows:** Device Manager → Ports (COM & LPT)
- **macOS/Linux:** `ls /dev/tty*` or `dmesg | grep tty`

---

---

## Step 7: Build and Upload

### Using PlatformIO GUI:
1. **Click the PlatformIO icon** in the left sidebar (alien head icon)
2. **Under "PROJECT TASKS" expand your environment** (e.g., esp32-s3-devkitc-1)
3. **Click "Build"** to compile the code first
4. **Wait for successful build** (check terminal output)
5. **Click "Upload"** to flash the ESP32

### Using PlatformIO Terminal:
1. **Open PlatformIO terminal:** Terminal → New Terminal
2. **Build the project:**
   ```bash
   pio run
   ```
3. **Upload to ESP32:**
   ```bash
   pio run -t upload && -t uploadfs
   ```

### Using VSCode Status Bar:
- **Click the checkmark (✓)** in the blue bottom bar to build
- **Click the arrow (→)** in the blue bottom bar to upload

---

## Step 8: Monitor Serial Output

1. **Click the monitor plug icon** in the blue status bar, or
2. **In PlatformIO sidebar:** expand your environment → click "Monitor"
3. **Or use terminal command:**
   ```bash
   pio device monitor
   ```

---

---

## Troubleshooting

### Upload Issues:
- **Wrong COM port:** Check device manager/system and update platformio.ini if needed
- **Board not in flash mode:** Try the BOOT+RESET procedure again
- **Driver issues:** Install ESP32 USB drivers from Espressif's website
- **Permission denied (Linux/macOS):** Add user to dialout group: `sudo usermod -a -G dialout $USER`

### Build Issues:
- **Missing libraries:** Check if libraries need to be installed (they'll be listed in build errors)
- **Wrong board config:** Verify your ESP32-S3 variant matches the platformio.ini settings

### Cannot find device:
```bash
# Check if device is detected
pio device list

# On Linux, you might need:
sudo chmod 666 /dev/ttyUSB0  # or your specific device
```

---

---

## WeighMyBru Specific Notes

Based on the project description, this scale project includes:
- **Webserver functionality** - After flashing, the ESP32 will host a web interface
- **WiFi connectivity** - You'll need to configure WiFi credentials
- **Bluetooth support** - For GaggiMate integration
- **HX711 load cell interface** - Make sure your hardware connections match the code

### Post-Flash Configuration:
1. **Connect to the ESP32's WiFi access point** (check serial monitor for details - AP IP :192.168.4.1)
2. **Access the web interface** for calibration and configuration
3. **Configure your home WiFi** through the web interface

---

## Success Indicators

✅ **Build completes without errors**  
✅ **Upload shows "SUCCESS" message**  
✅ **Serial monitor shows boot messages**  
✅ **ESP32 creates WiFi access point (for initial setup)**

Your WeighMyBru scale should now be running! Check the serial monitor for the web interface URL and initial setup instructions.