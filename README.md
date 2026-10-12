# ESP32-Based Wi-Fi Teleoperation Platform (Custom PCB)

**Status:** Ongoing

![Hardware](https://img.shields.io/badge/Hardware-Altium_Designer-blue.svg) ![MCU](https://img.shields.io/badge/MCU-ESP32--WROOM--32D-orange.svg) ![Connectivity](https://img.shields.io/badge/Connectivity-Wi--Fi%20%7C%20Blynk-brightgreen.svg)

## Overview

An end-to-end custom hardware design for a Wi-Fi-controlled, two-wheel-drive RC vehicle. Designed from scratch in Altium Designer, the board replaces jumper-wire prototyping with an integrated platform for wireless communication, motor driving and battery management.

## Hardware architecture

### Controller and connectivity

The ESP32-WROOM-32D is the main controller. The project uses the Blynk IoT platform for Wi-Fi teleoperation through a smartphone interface with joysticks, buttons and status monitors.

### Power management and protection

- **2S Li-ion battery management:** on-board cell protection using the HY2120 IC and 8205A MOSFETs, for charge/discharge protection and deep-depletion prevention.
- **Buck conversion:** an MP2307 converter steps the 2S battery input (approximately 7.4–8.4 V) down to 3.3 V for logic components.

### Motor drive and peripherals

- **DRV8833 dual motor driver:** drives two independent DC motors and includes thermal-shutdown and overcurrent protection.
- **Buzzer and LED headlights:** transistor-driven warning and status peripherals.

## PCB design approach

- Keep the ESP32 antenna area free of copper pours and traces.
- Separate analog/power sections from digital logic to reduce noise coupling.
- Use wider traces and copper pours for battery-to-motor-driver current paths.
- Use top- and bottom-layer ground pours with via stitching for return paths and board stability.

## Firmware and control

The firmware is written in C++ using the Arduino IDE framework. The Blynk smartphone interface provides remote control and status monitoring. Wi-Fi connectivity also supports potential remote-monitoring and internet-control use cases.

## Project visuals

Design visuals have not yet been added to this repository.

## About the designer

**Mert** — Electrical and Electronics Engineering student | Hardware Design Enthusiast

Designed with passion, driven by engineering principles.
