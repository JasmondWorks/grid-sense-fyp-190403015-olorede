# Grid Sense
### Smart Sub-Distribution Board Electrical Load Control System for Institutional Buildings

**Final Year Project | University of Lagos**

| Project Information | Details |
|---|---|
| Project Name | Grid Sense |
| Student Name | Obafemi Olorede |
| Matriculation Number | 190403015 |
| Department | Electrical/Electronics Engineering |
| Institution | University of Lagos |
| Project Category | Embedded Systems / Electrical Engineering |
| Microcontroller | ESP32-WROOM-32D |

**Project Repository:** `https://github.com/YOUR_USERNAME/grid-sense-fyp-190403015-olorede`

---

## 1. Overview

Grid Sense is an embedded electrical load control and monitoring system designed for institutional buildings.

The project focuses on improving how electrical loads within a building are managed through intelligent automation, scheduled operations, environmental monitoring and manual control.

The system is designed as a retrofit solution for an existing sub-distribution board, allowing selected electrical loads such as lighting points, fans, air-conditioning units and water pumps to be managed without requiring a complete redesign of the building's electrical installation.

An ESP32 microcontroller serves as the central control unit, coordinating connected sensors, switching devices and a locally hosted web application.

The web application provides an interface for monitoring the system, configuring operating schedules and managing electrical loads over a local wireless connection.

## 2. Project Objectives

The primary objectives of Grid Sense are to:

- Develop an intelligent load control system for institutional buildings.
- Automate selected electrical loads based on predefined schedules.
- Incorporate occupancy detection for intelligent lighting control.
- Monitor relevant environmental conditions to support automated control.
- Provide manual override functionality where necessary.
- Enable local wireless monitoring and configuration through a web-based interface.
- Reduce unnecessary energy consumption through coordinated load management.

## 3. System Features

The system is designed around five major functional areas:

### 3.1 Scheduled Load Control
Allows electrical loads to operate according to predefined schedules using a real-time clock.

### 3.2 Occupancy-Based Control
Uses motion detection to support automatic control of selected lighting circuits based on room occupancy.

### 3.3 Environmental Monitoring
Uses connected sensors to monitor environmental conditions and support appropriate control decisions.

### 3.4 Manual Override
Provides administrators with the ability to manually control selected loads when automatic operating conditions need to be overridden.

### 3.5 Local Web-Based Monitoring and Management
Provides a locally hosted web application for monitoring system status, managing configurations and controlling supported electrical loads.

## 4. System Architecture

Grid Sense uses an ESP32-based embedded architecture.

The ESP32 acts as the central controller and hosts the web application directly, eliminating the requirement for an external web server or cloud database for normal system operation.

The system consists of the following major components:

| Component | Responsibility |
|---|---|
| ESP32-WROOM-32D | Main system controller and local web server |
| DS3231 RTC | Accurate timekeeping for scheduled operations |
| PIR Sensor | Occupancy and motion detection |
| DS18B20 | Temperature monitoring |
| Relay Modules | Electrical load switching |
| Float Switches | Water-level-related control inputs |
| Push Button | Physical authorization for administrative password reset |
| LED Indicator | Visual indication of password reset confirmation mode |

*Refer to the hardware documentation for the complete circuit connections and component specifications.*

## 5. How the System Works

The ESP32 coordinates the connected sensors, switching devices and control logic.

The system operates independently of an internet connection. Its web application is served directly from the ESP32's internal flash storage over a local Wi-Fi connection.

The controller continuously executes its automation and monitoring functions, whether or not a user is connected to the web application.

### Wireless Access

Grid Sense operates using a Wi-Fi Access Point hosted by the ESP32.

Users connect directly to the wireless network broadcast by the device. A captive portal is implemented to automatically present the web interface when a supported phone or computer joins the network.

The local web application can also be accessed manually through:

`http://192.168.4.1`

### Authentication

The wireless access point and administrative portal use the same system PIN.

The system PIN is required to connect to the protected wireless network and authenticate administrative access.

Administrators can change their credentials through the administrative interface.

### Physical Password Recovery

For security, password recovery requires physical access to the device.

The recovery procedure uses a dedicated push button and LED indicator:

1. Hold the designated button for the required duration to initiate recovery mode.
2. The LED begins blinking to indicate that confirmation mode is active.
3. Hold the button again within the confirmation window to authorize the reset.
4. If confirmation is not completed within the allowed period, the operation is cancelled automatically.
5. Following successful authorization, the administrator can establish a new system PIN.

This mechanism helps prevent unauthorized password resets through the web interface alone.

## 6. Getting Started

### 6.1 For End Users

This section is intended for individuals using an already assembled and configured Grid Sense device.

**Requirements:**
- An operational Grid Sense unit.
- A smartphone, tablet or computer with Wi-Fi capability.
- The current system PIN.

**Connection instructions:**

1. Power on the Grid Sense unit.
2. Open the Wi-Fi settings on your device.
3. Locate and select the Grid Sense wireless network.
4. Enter the system PIN when prompted.
5. Wait for the captive portal to open automatically.
6. If the portal does not open automatically, navigate to `http://192.168.4.1` in your browser.
7. Authenticate using the same system PIN to access the administrative interface.

Once authenticated, you can access the monitoring and management features available on the device.

### 6.2 For Developers

Developers interested in building, modifying or contributing to the project can use the following setup instructions.

**Requirements:**

- Visual Studio Code
- PlatformIO IDE extension
- Git
- ESP32-WROOM-32D development board
- USB data cable

**Installation:**

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/grid-sense-fyp-190403015-olorede.git
   ```

2. Navigate into the project directory:

   ```bash
   cd grid-sense-fyp-190403015-olorede
   ```

3. Open the project in Visual Studio Code.

4. Install the PlatformIO IDE extension if it is not already installed.

5. Connect the ESP32 development board to your computer.

6. Open the PlatformIO project and install the required dependencies.

7. Build the firmware and upload it to the ESP32.

8. Upload the web application files to the ESP32 filesystem.

9. Restart the device and follow the end-user connection instructions.

*Note: Developer installation instructions and firmware upload procedures will be updated as the implementation progresses.*

## 7. Hardware and Software Requirements

### Hardware

- ESP32-WROOM-32D development board.
- DS3231 real-time clock module.
- PIR motion sensor.
- DS18B20 temperature sensor.
- Float switches.
- Relay modules.
- Push button and LED indicators.
- Supporting power supply, protection and electrical interface components.

### Software and Development Tools

| Tool | Purpose |
|---|---|
| PlatformIO | Embedded development environment |
| Visual Studio Code | Code editor |
| Arduino Framework | ESP32 firmware development |
| C++ | Embedded application logic |
| HTML, CSS and JavaScript | Web application |
| LittleFS | Web application file storage |
| ESP32 WebServer | Local HTTP server |
| ESP32 DNSServer | Captive portal DNS handling |
| Preferences (NVS) | Persistent configuration storage |

## 8. Repository Structure

The repository is organized into the following major sections:

```text
grid-sense-fyp-190403015-olorede/
│
├── firmware/       # ESP32 firmware
├── web/            # Captive portal and admin interface
├── hardware/       # Circuit diagrams and hardware documentation
├── docs/           # Project and user documentation
├── assets/         # Images, diagrams and screenshots
│
├── README.md
├── LICENSE
└── .gitignore
```

Individual directories will contain additional documentation as development progresses.

## 9. Project Documentation

Technical documentation, hardware diagrams, system architecture and user instructions will be maintained in the `docs/` and `hardware/` directories.

The repository will serve as the central location for project documentation and implementation updates.

## 10. Development Status

Grid Sense is currently under development.

The repository is being established as the central project documentation and source-code repository. Firmware development, web application implementation, hardware integration and system testing will be documented and committed incrementally.

Implementation status will be updated as individual components are completed and validated.

## 11. Safety Considerations

Grid Sense is designed to interact with electrical distribution infrastructure.

All electrical connections, switching components, protective devices and enclosure arrangements must be designed and implemented with appropriate electrical safety precautions.

The low-voltage control electronics must be properly isolated from mains-voltage circuits.

Testing and installation should be carried out under appropriate supervision by qualified personnel.

## 12. Project Author

**Obafemi Olorede**

Department of Electrical/Electronics Engineering  
University of Lagos

Matriculation Number: **190403015**

---

*Grid Sense — Intelligent Electrical Load Management for Institutional Buildings.*
