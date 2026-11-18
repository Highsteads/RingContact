# Ring Contact for Indigo

Use a **Ring Alarm Contact Sensor (2nd Generation)** as an **Open** or **Closed** device in Indigo and use either change in your automations. The plugin runs on the Indigo Mac with a dedicated Z-Wave USB stick, without Home Assistant.

**Version 0.1.1** · **Indigo 2025.2 or 2026.1** · **Node.js 22 or later**

[Download the plugin ZIP](./Ring%20Contact%200.1.1.indigoPlugin.zip?raw=1) · [Read the setup guide](./Ring%20Contact%20Setup%20Guide.md)

## What it does

- Shows each paired sensor as a door or window device in Indigo.
- Uses Indigo’s normal device-state triggers for opening and closing.
- Shows the battery level and tamper status when the sensor reports them.

## Getting started

1. Install Node.js on the Mac that runs Indigo and connect the dedicated Z-Wave stick. The setup guide uses the **Aeotec Z-Stick 10 Pro**.
2. Unzip the download and double-click **Ring Contact.indigoPlugin**. Choose the stick in the plugin settings, then select **Install or Repair Driver**.
3. Choose **Add Ring Sensor**, follow the pairing steps, and look under **Devices → Ring**. Move the magnet away and back to check that Indigo shows **Open** and **Closed**.

The first driver installation needs internet access. If your Ring sensor is already paired elsewhere, follow the [setup guide](./Ring%20Contact%20Setup%20Guide.md) to move it. If you already use a Gen5 with Indigo, use the 10 Pro for the Ring sensors and the Gen5 for your other Z-Wave devices.

## Testing status

This is an early test build. Driver installation and simulated open and close events passed testing. Pairing and reporting with a real Ring sensor still need to be verified. Try one sensor first and share your results in the [Indigo forum discussion](https://forums.indigodomo.com/viewtopic.php?t=29230).
