# Software Setup

💻 Installing VSCode & PlatformIO for ESP32 Development

If you're planning to build a WeighMyBru scale, you'll need to flash firmware onto the ESP32 board. The best tool for this is [Visual Studio Code](https://code.visualstudio.com/) with the [PlatformIO](https://platformio.org/) extension.

Here is a link to a [video](https://www.youtube.com/watch?v=MeIcL9igsbM) if you're not interested in reading.


---

## Step 1: Install Visual Studio Code

1. Go to the [official VSCode download page](https://code.visualstudio.com/).
2. Click **Download for Windows/macOS/Linux** depending on your operating system.
3. Run the installer and follow the prompts.
   - On Windows, ensure you check the box that says **“Add to PATH”** (this makes launching VSCode from terminal/cmd easier).
4. After installation, open **Visual Studio Code**.

---

## Step 2: Install PlatformIO Extension

1. Launch **Visual Studio Code**.
2. Go to the **Extensions** view:
   - Click the square icon on the left sidebar (or press `Ctrl+Shift+X` / `Cmd+Shift+X`).
3. In the search bar, type: `PlatformIO IDE`
4. Click **Install** on the “PlatformIO IDE” extension by `PlatformIO Labs`.
5. Wait for installation to complete. It may take a few minutes.
6. After it installs, PlatformIO will initialize its environment. Let it finish.

---

## Step 3: Verify PlatformIO is Working

1. Click on the **alien head icon** (⚙️ PIO) on the left sidebar – this opens the **PlatformIO Home**.
2. From here, you can:
   - Create or open projects
   - Access the library manager
   - Open terminal (for `pio run`, `pio upload`, etc.)

---

## Step 4: Install USB Drivers (if needed)

For most ESP32 boards, Windows users may need **USB-to-Serial drivers** (e.g. CP2102 or CH340):

- **CH340 driver**: [https://sparks.gogo.co.nz/ch340.html](https://sparks.gogo.co.nz/ch340.html)
- **CP210x driver**: [https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)

Install the correct driver based on your board's chip. You can find this info on the board or from the seller.

---

## Step 5: Open or Clone Your Project

To open your WeighMyBru firmware:

- Click `Open Project` in PlatformIO Home and navigate to the folder.
- Or use Git:
  1. Open VSCode terminal (`Ctrl+``)
  2. Run:
     ```bash
     git clone https://github.com/yourusername/weighmybru.git
     cd weighmybru
     ```

VSCode will automatically detect the `platformio.ini` file and open it as a PlatformIO project.

---

## Step 6: Connect Your ESP32 and Upload Firmware

1. Plug in your ESP32 board using a USB cable.
2. In VSCode, open the **PlatformIO toolbar** at the bottom.
3. Click the **Upload (arrow)** button.
4. PlatformIO will compile and upload the firmware to your ESP32.

> 🟢 You should see a success message like `SUCCESS: [program] has been uploaded`.

---

**Optional: Monitor Serial Output**

- Click the **Monitor (plug icon)** in PlatformIO to view the ESP32 serial output (useful for debugging).
- Default baud rate is usually `115200` — you can change it in `platformio.ini`.

---

**Done!**

You're now ready to develop, modify, and flash firmware onto your WeighMyBru scale.

> 💡 Tip: If this is your first time using VSCode or PlatformIO, take your time exploring the interface. It's a powerful toolkit and well-suited for ESP32 development.

