# Ring Contact for Indigo

Use a Ring Alarm Contact Sensor (2nd Generation) as an **Open** or **Closed** sensor in Indigo. This first build is ready for a trial with one sensor. Pairing and reporting still need to be verified on real hardware.

## Set up the Mac and USB stick

1. On the Mac running **Indigo 2025.2 or 2026.1**, install **Node.js 22 or later**. Choose the official **Node.js 22 macOS Installer** for an older Mac. That installer requires macOS 11 Big Sur or later. [Node.js downloads](https://nodejs.org/en/download)
2. If the Ring sensor you want to try is already in Home Assistant, remove just that sensor there while the **Aeotec Z-Stick 10 Pro** is still connected. Then stop the program using the 10 Pro and move the stick to the Indigo Mac. Any other sensors paired to that 10 Pro will stop reporting to Home Assistant while the stick is with Indigo. Keep your existing Indigo devices on the Gen5. [Removing a device in Home Assistant](https://www.home-assistant.io/integrations/zwave_js/#removing-a-device-from-the-current-z-wave-network)
3. Unzip the download and double-click **Ring Contact.indigoPlugin**. In Indigo, open **Plugins → Ring Contact → Configure…**. Choose the 10 Pro’s USB port and save. Leave the **Node.js path** blank if you used the standard installer.
4. Choose **Plugins → Ring Contact → Install or Repair Driver**. This step needs internet access to download the driver. Watch the **Event Log** and wait for **Z-Wave stick is ready**. The 10 Pro can show two ports. If the stick doesn’t answer, try its other port in **Configure…**. [Aeotec’s USB stick guide](https://aeotec.freshdesk.com/support/solutions/articles/6000274575)

## Add and test one sensor

1. Bring the sensor close to the stick. In **Plugins → Ring Contact → Add Ring Sensor…**, enter the five digits printed below the sensor’s QR code. Click **Start Pairing**. When the Event Log says pairing has started, hold the front button for about three seconds and release it. [Ring’s pairing guide, page 3](https://assets.ctfassets.net/jrz4hnnvdyct/3AXPQshkruQCZPoSNuSzGp/05de23a6f2c261a00b4752cb9b722c9b/Ring_Alarm_Contact_Sensor_Gen_2_Zwave_NA.pdf#page=3)
2. Open **Devices → Ring** in Indigo. The plugin creates this folder when it adds its first sensor. Move the magnet away and then back. You should see **Open** and **Closed**. The first confirmed reading sets the starting state and later changes can run a trigger.
3. Create a **Device State Changed** trigger for the Ring device. Choose **On State** and use **On** for opening or **Off** for closing. If you already have a trigger that uses the Home Assistant copy of the sensor, select the new Ring Contact device in that trigger. Test it by opening and closing the door again. Once one sensor works, clear the next sensor’s old pairing before adding it.

If a sensor still has an old pairing and you can’t remove it from its former setup, choose **Plugins → Ring Contact → Remove Ring Sensor…** and click **Start Removal**. Briefly press the sensor’s reset pinhole with a paper clip, then try pairing again. [Ring’s removal instructions, page 4](https://assets.ctfassets.net/jrz4hnnvdyct/3AXPQshkruQCZPoSNuSzGp/05de23a6f2c261a00b4752cb9b722c9b/Ring_Alarm_Contact_Sensor_Gen_2_Zwave_NA.pdf#page=4)
