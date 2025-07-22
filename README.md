# BSC Boley/S4565 Honeywell Control User Manual

Welcome to the **BSC Boley/S4565 Control/** system! This guide is designed for beginners to help you understand and use your fireplace control system easily. The system allows you to control your fireplace through a web interface, a remote control, or home automation systems. Follow this simple manual to get started.

---

## Table of Contents
1. [What is the BSC Boley/S4565 Honeywell Control?](#what-is-the-bsc-boley-control)
2. [Getting Started](#getting-started)
   - Connecting to the System
   - Accessing the Web Interface
3. [Using the Web Interface](#using-the-web-interface)
   - Home Page
   - Settings Page
   - Remote Page
   - Domotica Page
4. [Using the IR Remote](#using-the-ir-remote)
5. [Safety Features](#safety-features)
6. [Troubleshooting](#troubleshooting)
7. [Contact and Support](#contact-and-support)

---

## What is the BSC Boley Control?

The BSC Boley Control is a smart system for controlling your fireplace. It manages the fireplace's fans, valves, and safety features. You can control it using:
- A **web browser** on your phone, tablet, or computer.
- An **IR remote control** (like a TV remote).
- A **home automation system** (via Modbus TCP/IP or analog input).

The system ensures safe operation by monitoring sensors and automatically stopping if something goes wrong.

---

## Getting Started

### Connecting to the System
1. **Power On the Device**: Ensure the fireplace control unit is plugged in and powered on.
2. **Connect to Wi-Fi**:
   - The device creates its own Wi-Fi network called **BSC Boley Control GRS²** with the password **12345678**.
   - Alternatively, you can connect it to your home Wi-Fi (see Settings Page below).
3. **Find the IP Address**:
   - If using the device's Wi-Fi, the IP address is usually **192.168.4.1**.
   - If connected to your home Wi-Fi, check your router or the device's Settings page for the IP address.

### Accessing the Web Interface
1. Open a web browser (e.g., Chrome, Safari) on your phone, tablet, or computer.
2. Type the IP address (e.g., **192.168.4.1**) into the address bar and press Enter.
3. You should see the **BSC Boley Control** home page.

---

## Using the Web Interface

The web interface has four main pages: Home, Settings, Remote, and Domotica. Each page helps you control or configure the system.

### Home Page
The Home page is your main control panel. Here’s what you can do:
- **Check Status**:
  - See if the fireplace is ON or OFF.
  - View safety statuses (e.g., Thermal Protection, Limit Switches, Faults).
  - Check burning hours and fault counts.
- **Control the Fireplace**:
  - **Start**: Click the "Start" button to turn on the fireplace. The system checks safety sensors before starting.
  - **Stop**: Click the "Turn Off" button to stop the fireplace.
  - **Reset**: If a fault occurs, click "Reset" to clear it.
- **Adjust Fans and Valve**:
  - **Exhaust Fan Speed**: Use the slider to set the exhaust fan speed (0-100%). Note: This is disabled if PDS (Pressure Differential Sensor) is active.
  - **Inlet Fan/Output**: Choose the mode (Inlet Fan, User Output, or Second Valve) and adjust the speed or state.
  - **Valve Duty Cycle**: Adjust the flame intensity (0-100%) using the slider when the fireplace is ON.
  - **Wave Function**: Check the box to enable a random flame effect.
- **Safety Override**: Check the box and enter the password (**admin123**) to bypass safety checks temporarily (auto-disables after 5 minutes).
- **Reset Counters**: Click to reset burning hours and fault counts (requires password **admin123**).

### Settings Page
The Settings page lets you configure the system:
- **Wi-Fi Configuration**:
  - **Scan Network**: Click to see available Wi-Fi networks.
  - **Connect to Wi-Fi**: Select a network, enter the password, and optionally set a static IP address.
  - **Switch to AP Mode**: Return to the device's own Wi-Fi network.
- **Firmware Update**:
  - **Manual Update**: Upload a `.bin` firmware file to update the system.
  - **OTA Update**: If a new version is available, click "Update Now OTA" to download and install it.
- **Full Reset**: Reset the device to factory settings (erases all settings).

### Remote Page
The Remote page configures an IR remote control:
- **Learn IR Codes**:
  - Click "Learn" next to a function (e.g., Start, Stop, Flame UP, Flame DOWN, Wave Activate).
  - Press the desired button on your IR remote within 5 seconds.
  - The system will save the code or show an error if it fails.
- **Clear IR Codes**: Click to remove all saved IR codes.
- **View Codes**: See the current IR codes for each function.

### Domotica Page
The Domotica page integrates with home automation systems:
- **Analog Input**:
  - Enable to control the fireplace with an analog voltage signal:
    - 0-1.8V: Stops the system.
    - 2-8V: Starts the system and adjusts the flame.
    - >8V: Activates the wave function.
  - View the current voltage on a progress bar.
- **Modbus TCP/IP**:
  - Connect to the device using a Modbus client (IP address shown, port 502, slave ID 2).
  - Control the fireplace (start/stop, valve, wave function) and read statuses (burning hours, faults).

---

## Using the IR Remote

After setting up IR codes on the Remote page:
- **Start**: Press the programmed button to start the fireplace.
- **Stop**: Press to stop the fireplace.
- **Flame UP/DOWN**: Adjust the flame intensity (only works when the fireplace is ON and safe).
- **Wave Activate**: Turn on the random flame effect.

Ensure the remote is pointed at the IR receiver on the device.

---

## Safety Features

The system has built-in safety checks:
- **Thermal Recoil Protection**: Stops the fireplace if it overheats.
- **Limit Switches**: Ensures inlet and outlet paths are clear.
- **Fault Input**: Detects external faults and stops the system.
- **PDS (Pressure Differential Sensor)**: Adjusts exhaust fan speed to maintain safe pressure (if enabled).
- **Safety Override**: Temporarily bypasses safety checks with the password **admin123** (use with caution).

If a fault occurs, the LED on the device blinks to indicate the issue:
- 1 blink: Thermal fault.
- 2 blinks: Limit switch fault.
- 3 blinks: Fault input active.
- 4 blinks: PDS failure.

The fireplace stops automatically if a fault is detected, and you may need to press "Reset" to clear it.

---

## Troubleshooting

- **Can’t Connect to Wi-Fi**:
  - Ensure you’re connected to **BSC Boley Control GRS²** or your home Wi-Fi.
  - Check the IP address in the Settings page.
- **Fireplace Won’t Start**:
  - Check the Home page for error messages (e.g., limit switch open, fault active).
  - Ensure safety override is enabled if bypassing checks.
- **IR Remote Not Working**:
  - Verify IR codes are programmed correctly.
  - Point the remote directly at the device’s IR receiver.
- **Firmware Update Fails**:
  - Ensure a stable Wi-Fi connection.
  - Check the Settings page for error messages.
- **LED Blinking**:
  - Count the blinks to identify the fault (see Safety Features).
  - Press "Reset" on the Home page or use the IR remote.

---

## Contact and Support

For help, visit **www.grss.be** or contact the developer, Kevin De Bosscher, via the website. Ensure you have the device’s IP address and any error messages when seeking support.

---

This manual should help you get started with your BSC Boley Control system. Enjoy your smart fireplace experience!
