# BSC Boley/S4565 Honeywell Control User Manual

Welcome to the **BSC Boley/S4565 Control/** system! This guide is designed for beginners to help you understand and use your fireplace control system easily. The system allows you to control your fireplace through a web interface, a remote control, or home automation systems. Follow this simple manual to get started.

---


🔥
BSC/S4565 Controller
User Manual
Honeywell S4565 Fireplace Control System
Version 2.0.1
GRS²
www.grss.be

Table of Contents
1. Introduction
2. Getting Started
3. Web Interface Overview
4. Home Page - Main Controls
5. Settings Page
6. Statistics Page
7. Event Log
8. Remote Control Setup
9. Home Automation Integration
10. Safety Features
11. Maintenance
12. Troubleshooting
13. Technical Specifications

1. Introduction
The BSC/S4565 Controller is an advanced smart control system designed for Honeywell S4565-based gas fireplaces. This ESP-based controller provides comprehensive management of your fireplace through multiple interfaces:
Web-based interface accessible from any device
IR/RF remote control support
Home automation integration via Modbus TCP/IP HomeAssistent compatible
Analog voltage control (0-10V)

1.1 Key Features
Real-time monitoring of all safety systems
Adjustable flame intensity with PWM valve control
Automatic fan speed management with PDS support
Wave function for natural flame effect
Second valve/output control for dual-burner systems
Comprehensive statistics and event logging
Email alerts for faults and maintenance
Over-the-air (OTA) firmware updates

⚠ WARNING: This controller manages gas-burning equipment. Always ensure proper installation by a qualified technician. Never bypass safety features during normal operation.

2. Getting Started
2.1 Initial Connection
When powered on for the first time, the controller creates its own WiFi network:

Setting
Value
Network Name (SSID)
BSC/S4565 Control - GRS²
Password
12345678
IP Address
192.168.4.1
Default Login Password
admin

2.2 Connecting to Your Home WiFi
1. Connect to the controller's WiFi network
2. Open a web browser and navigate to 192.168.4.1
3. Log in with password: admin
4. Go to the Settings page
5. Click 'Scan Networks' to find available WiFi networks
6. Select your network and enter the password
7. Click 'Connect' - the device will restart

ℹ After connecting to your home WiFi, you can access the controller using its new IP address or via mDNS: http://fireplace.local (if supported by your network).

3. Web Interface Overview
The web interface provides full control and monitoring through five main pages:

Page
Description
Home
Main control panel - start/stop, fan control, valve adjustment
Settings
WiFi configuration, email alerts, maintenance, firmware updates
Statistics
Burning hours, start counts, charts, and usage history
Event Log
History of system events, faults, and actions
Remote
IR/RF remote control learning and configuration

4. Home Page - Main Controls
4.1 System Status
The status section displays real-time information about all safety systems:

Indicator
Meaning
Thermal Recoil
Overheat protection sensor status (Inactive = OK)
Limit Switch
Door/airflow safety switch (Closed = OK)
Fault Input
External fault signal from S4565 (Inactive = OK)
Start SSR
Main burner solid-state relay (ON = Burning)
PDS Status
Pressure Differential Sensor (Active = Fan auto-control)

4.2 Start/Stop Controls
Start Button: Initiates the fireplace startup sequence. The system performs safety checks before ignition.
Stop Button: Safely shuts down the fireplace. The exhaust fan continues running for a cool-down period.
Reset Button: Clears fault conditions after the underlying issue has been resolved.

4.3 Fan Controls
Exhaust Fan
Controls the speed of the exhaust/chimney fan (0-100%). When PDS is enabled, this is automatically managed to maintain proper pressure differential.

Output 2 / Second Valve
The second output can be configured in three modes:
Mode 0 - Inlet Fan: PWM-controlled inlet fan speed
Mode 1 - User Output: General purpose PWM output
Mode 2 - Second Valve: On/off control for dual-burner systems

4.4 PWM Valve Control
The PWM valve controls flame intensity from 0-100%. This slider is only active when the fireplace is running.

Wave Function
When enabled, the flame intensity varies randomly to create a more natural, realistic fire appearance. 


5. Settings Page
5.1 WiFi Configuration
Configure network connectivity:
Scan Networks: Discover available WiFi networks
Static IP: Optionally configure a fixed IP address
AP Mode: Switch back to Access Point mode

5.2 Email Alerts
Configure automatic email notifications for:
Fault detection
Maintenance reminders
Auto-shutdown events

Up to 3 email recipients can be configured. SMTP server settings pre-configured via our server.Notifications will be send from fireplaceATgrss.be

5.3 Maintenance Settings
Maintenance Interval: Set the number of operating hours between maintenance reminders (default: 300 hours).
Reset Maintenance: Clear the maintenance counter after service has been performed (requires admin password).

5.4 Auto-Shutdown
Configure automatic shutdown after a set number of hours of continuous operation. This is a safety feature to prevent unattended extended use.

5.5 Firmware Updates
Manual Update
Upload a firmware .bin file directly through the web interface.

OTA (Over-The-Air) Update
When connected to the internet, the system automatically checks for updates. If available, click 'Update Now' to download and install the latest firmware.

⚠ WARNING: Do not power off the device during a firmware update. This may corrupt the firmware and require manual recovery

6. Statistics Page
The Statistics page provides comprehensive usage data and historical tracking.

6.1 Counters
Counter
Description
Burning Hours
Total hours of main burner operation
Pilot Burning Hours
Hours of pilot flame operation
Second Valve Hours
Total hours second valve/burner active
Start Count
Number of successful ignition cycles
Fault Count
Total number of fault events recorded

6.2 Charts
Interactive charts display the last 30 days of:
Daily burning hours
Start counts per day
Average valve position
Second valve usage (if applicable)

7. Event Log
The Event Log records all significant system events with timestamps. Events are stored in non-volatile memory and persist through power cycles.

7.1 Event Types
Event
Description
SYSTEM_START
Controller powered on/restarted
FIRE_ON / FIRE_OFF
Fireplace started or stopped
FAULT_DETECTED
Safety fault triggered
FAULT_RESET
Fault condition cleared
SECOND_VALVE_ON/OFF
Second valve state changed
WIFI_CONNECTED
Network connection established
FIRMWARE_UPDATE
Firmware update completed

8. Remote Control Setup
The controller supports both IR (infrared) and RF (radio frequency) remote controls.

8.1 Supported Remote Types
IR Remote: Standard infrared remotes 
(RF Remote: Radio frequency remotes) under development
AM05 Remote: Pre-configured 

8.2 Learning Remote Codes
8. Navigate to the Remote page
9. Select your remote type (IR or RF)
10. Click 'Learn' next to the function you want to program
11. Press the desired button on your remote within 5 seconds
12. The system will confirm successful learning or show an error

8.3 Available Functions
Start/Stop: Toggle fireplace on/off
Flame Up: Increase flame intensity by 10%
Flame Down: Decrease flame intensity by 10%
Wave Activate: Toggle wave function
Reset: Reset function in case of error

9. Home Automation Integration
9.1 Modbus TCP/IP
The controller provides a Modbus TCP server for integration with home automation systems.
ModBus-Registers operations and details visible on UI
Setting
Value
Port
502 (standard Modbus TCP)
Slave ID
2

9.2 Analog Input Control
When enabled, the controller responds only to 0-10V analog signals:

Voltage Range
Action
0V - 1.8V
Stop fireplace
2.0V - 8.0V
Start and adjust flame intensity proportionally
> 8.0V
Enable wave function

10. Safety Features
The BSC/S4565 Controller incorporates multiple layers of safety protection.

10.1 Safety Systems
Thermal Recoil Protection
Monitors the fireplace temperature. If overheating is detected, the system immediate shuts down.

Limit Switch Monitoring
Ensures that access doors are closed and airflow paths are clear before allowing operation.

Fault Input Detection
Monitors the S4565 control module's fault output. Any fault condition triggers immediate shutdown.

PDS (Pressure Differential Sensor)
When enabled, automatically adjusts exhaust fan speed to maintain safe chimnee draft.

10.2 LED Fault Indicators
The status LED indicates fault conditions through blink patterns:

Blink Pattern
Meaning
1 Blink
Thermal recoil fault
2 Blinks
Limit switch open
3 Blinks
Fault input active
4 Blinks
PDS failure
Solid On
System running normally
Breathing
Start Sequence


10.3 Safety Override
For diagnostic purposes, safety checks can be temporarily bypassed:
Requires admin password
Automatically disables after 5 minutes
Should only be used by qualified technicians

⚠ WARNING: Safety override bypasses critical protection systems. Only use during installation and troubleshooting by qualified personnel. Never leave unattended with safety override enabled.

11. Maintenance
11.1 Regular Maintenance Schedule
The controller tracks operating hours and reminds you when maintenance is due. Recommended service interval: 300 hours (adjustable in Settings).

11.2 Maintenance Checklist
Inspect and clean the exhaust fan
Check all gas connections for leaks
Clean the burner assembly
Verify safety sensor operation
Test all control functions
Reset the maintenance counter after service

11.3 Resetting Maintenance Counter
13. Navigate to Settings page
14. Scroll to Maintenance section
15. Click 'Reset Maintenance Counter'
16. Enter admin password when prompted

12. Troubleshooting
12.1 Common Issues

Cannot Connect to Web Interface
Verify you're connected to the correct WiFi network
Try the direct IP address instead of mDNS hostname
Power cycle the controller
Check if AP mode is active (connect to BSC/S4565 Control network)

Fireplace Won't Start
Check status indicators for fault conditions
Verify all safety sensors show OK status
Try the Reset button if a fault is indicated
Check the Event Log for error details

Remote Control Not Working
Verify remote type matches settings (IR/RF)
Re-learn the remote codes
Check remote battery
Ensure clear line-of-sight for IR remotes

Flame Intensity Not Adjusting
Fireplace must be running to adjust flame
Verify PWM valve wiring

12.2 Factory Reset
If all else fails, perform a factory reset:
17. Navigate to Settings page
18. Scroll to bottom and click 'Full Reset'
19. Confirm the reset
20. Device will restart with default settings

⚠ WARNING: Factory reset erases ALL settings including WiFi configuration, learned remote codes, and statistics. Use only as a last resort.

13. Technical Specifications

Parameter
Specification
Processor
ESP Dual-Core
WiFi
802.11 b/g/n 2.4GHz
PWM Outputs
3x 8-bit (Exhaust, Inlet/Valve, PWM Valve)
Digital Inputs
Thermal, Limit Switch, Fault, PDS
Analog Input
0-10V (via voltage divider)
IR Receiver
38kHz compatible
RF Receiver
(433MHz)
Communication
Modbus TCP/IP (Port 502)
Storage
EEPROM + LittleFS
Statistics Retention
30 days daily history
Watchdog Timer
60 second timeout
**Laagspanningsrichtlijn 2014/35/EU** (Low Voltage Directive) - **EMC-richtlijn 2014/30/EU** (Electromagnetic Compatibility) - **RoHS-richtlijn 2011/65/EU** (Restriction of Hazardous Substances) - **Radio Equipment Directive 2014/53/EU** (voor WiFi-functionaliteit)
EN 60204-1:2018 - Veiligheid van machines - Elektrische uitrusting - EN 61010-1:2010 - Veiligheid elektrische meet-, regel- en laboratoriumapparatuur 
EN 55032:2015 - Multimedia apparatuur - EMC-eisen - Emissie - EN 55035:2017 - Multimedia apparatuur - EMC-eisen - Immuniteit - EN 301 489-1 V2.2.3 - EMC voor radio-apparatuur - Algemene eisen - EN 301 489-17 V3.2.4 - EMC voor breedband datatransmissiesystemen 
EN 300 328 V2.2.2 - 2,4 GHz breedband transmissiesystemen - EN 62479:2010 - SAR-beoordeling draadloze communicatieapparatuur 
EN 50581:2012 - Documentatie voor RoHS-conformiteitsbeoordeling 

GRS²
www.grss.be
© 2025 - All Rights Reserved
