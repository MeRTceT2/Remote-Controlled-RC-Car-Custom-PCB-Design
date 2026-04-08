#  ESP32-Based Wi-Fi Teleoperation Platform (Custom PCB) (Ongoing)

[![Hardware](https://img.shields.io/badge/Hardware-Altium_Designer-blue.svg)](#)
[![MCU](https://img.shields.io/badge/MCU-ESP32--WROOM--32D-orange.svg)](#)
[![Connectivity](https://img.shields.io/badge/Connectivity-Wi--Fi%20%7C%20Blynk-brightgreen.svg)](#)

##  Project Overview
This project is an end-to-end custom hardware design for a Wi-Fi-controlled, 2WD remote-control vehicle. Designed entirely from scratch in **Altium Designer**, the primary goal was to eliminate the "messy jumper wire" approach commonly found in hobby projects and replace it with a robust, industrial-grade motherboard. 

This custom PCB serves as the central brain and power distribution network, seamlessly integrating wireless communication, motor driving infrastructure, and a native battery management system into a single, reliable platform.

![3D PCB Render](link_to_your_3D_view_image_here)

---

##  Key Features & Hardware Architecture
The system is divided into carefully engineered functional blocks to ensure stability, safety, and performance.

###  Microcontroller & Connectivity
* **ESP32-WROOM-32D:** Acts as the main processing unit, selected for its dual-core performance and built-in PCB antenna. It handles low-latency Wi-Fi communication via the **Blynk IoT Platform**, allowing for seamless teleoperation over long distances.

###  Custom Power Management & Protection
* **On-Board 2S Li-Ion BMS:** Instead of using off-the-shelf modules, native cell protection was implemented using the **HY2120 IC** and **8205A MOSFETs**. This ensures safe charging/discharging and prevents deep depletion of the batteries.
* **Switch-Mode Power Supply (SMPS):** A high-efficiency **MP2307 Buck Converter** steps down the 2S battery voltage (~7.4V - 8.4V) to a stable 3.3V for the logic-level components, preventing the thermal issues associated with linear regulators.

###  Motor Drive & Peripherals
* **DRV8833 Dual Motor Driver:** Drives two independent DC motors efficiently. It features built-in thermal shutdown and overcurrent protection, making the platform highly durable against stalled motors.
* **Integrated Peripherals:** Includes discrete transistor-driven circuits for a high-decibel warning horn (Buzzer) and LED headlights for status indication and night operations.

![Schematic Diagram](link_to_your_schematic_image_here)

---

##  Applied PCB Design Techniques
The board was developed adhering to professional PCB layout principles, treating power electronics and RF communication with the respect they require:

* **EMI Mitigation & Signal Integrity:** The ESP32 antenna section is kept completely free of copper pours and traces. Analog/power sections are physically separated from digital logic sections to prevent noise coupling.
* **Power Routing & Thermal Management:** High-current traces (from the battery to the motor driver) were calculated and routed with significant width and polygon pours to prevent voltage drops and thermal throttling.
* **Continuous Ground Planes:** Both top and bottom layers utilize extensive copper ground pours (GND) with adequate via stitching to provide the shortest possible return paths and improve overall stability.

![PCB Layout](link_to_your_layout_image_here)

---

##  Firmware & Control Interface
The firmware is written in **C++** (Arduino IDE framework). The platform is controlled remotely using the **Blynk App**, which provides a highly responsive, custom-built user interface (joysticks, buttons, and status monitors) right on a smartphone. 

Because the system relies on Wi-Fi rather than classic Bluetooth, it opens up possibilities for true IoT applications, including remote monitoring and control over the internet.

---

##  About the Designer
**Mert** *Electrical and Electronics Engineering Student | Hardware Design Enthusiast*

Designed with passion, driven by engineering principles.
