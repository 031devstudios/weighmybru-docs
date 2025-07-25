## WebUI

Once you have successfully flashed the firmware onto the ESP32 microcontroller and rebooted the device, a Wi-Fi access point named **`WeighMyBru-AP`** will become available. Connect to this access point using your mobile device.

After connecting, open a web browser and navigate to: [http://weighmybru.local](http://weighmybru.local)


This will take you to the WebUI in **Access Point (AP) mode**.

<div style="display: flex; gap: 20px;">
  <div style="text-align: center;">
    <p>AP Mode</p>
    <img src="media/webui/webui-ap.jpeg" alt="WebUI-AP" width="300" height="400">
  </div>
  <div style="text-align: center;">
    <p>STA Mode</p>
    <img src="media/webui/webui-sta.jpeg" alt="WebUI-STA" width="300" height="400">
  </div>
</div>

> ⚠️ Note: If the interface does not match the screenshots shown in the documentation, don't be concerned. When the scale is not connected to the internet, the WebUI cannot load its styling assets from the CDN (Content Delivery Network). Once internet access is established, the full themed interface will be visible.

---

## WebUI Features

The WebUI allows you to view:

- **Current weight**
- **Real-time flow rate**

You will also gain access to the following tools:

- [Calibration](/usage/calibration.md)
- [Settings](/usage/settings.md)
- [Updates](/advanced/ota.md)

Use the sidebar navigation to explore these sections in more detail.

---

## Connecting to Wi-Fi

To unlock the full WebUI experience, including CDN styling, you'll need to connect the scale to your local Wi-Fi network.

Navigate to the [Wi-Fi Setup](/integration/wifi.md) page within the WebUI, and enter your Wi-Fi credentials.

Once connected to a network with internet access, the WebUI will load completely with full styling and features.

---
