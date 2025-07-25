# Settings

The **Settings** page allows you to configure key features of your WeighMyBru scale, including Wi-Fi connectivity and display precision.
<img src="media/usage/settings.png" alt="WebUI-AP" width="600" height="400"><br>

---

## 📡 Wi-Fi Configuration

You can connect the scale to your home or work network by entering the SSID and password on this page.

### Steps:
1. Enter your **Wi-Fi SSID** and **password** into the respective input fields.
2. Click the **Save WiFi Settings** button.
3. A confirmation message will appear:  
   `"WiFi credentials saved. Reboot to connect."`
4. Reboot the scale.
5. Once connected, access the WebUI by opening a browser and visiting:  
   [`http://weighmybru.local`](http://weighmybru.local)

> ✅ The Wi-Fi credentials are securely saved to the ESP32's EEPROM memory, so you won’t need to re-enter them after rebooting.

---

## 🖥️ Display Settings

You can configure how the weight is displayed by choosing the desired number of decimal places.

### Options:
| Setting | Format  | Example   |
|---------|---------|-----------|
| `1`     | `0g`    | `25g`     |
| `2`     | `0.0g`  | `25.4g`   |
| `3`     | `0.00g` | `25.45g`  |

### Steps:
1. Select your preferred display format.
2. Click the **Save Display Settings** button.
3. A confirmation message will appear:  
   `"Decimal setting saved."`

> 💾 This preference is also stored in the ESP32's EEPROM and will persist after rebooting.

---

## 🔄 Need to Change It Later?

You can return to the **Settings** page at any time to:
- Update your Wi-Fi credentials.
- Adjust the display precision to suit your preference.

