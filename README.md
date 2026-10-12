# ESP32-Based Wi-Fi Teleoperation Platform (Custom PCB)

**Status:** Ongoing

![Hardware](https://img.shields.io/badge/Hardware-Altium_Designer-blue.svg) ![MCU](https://img.shields.io/badge/MCU-ESP32--WROOM--32D-orange.svg) ![Connectivity](https://img.shields.io/badge/Connectivity-Wi--Fi%20%7C%20Blynk-brightgreen.svg)

## Overview

An end-to-end custom hardware design for a Wi-Fi-controlled, two-wheel-drive RC vehicle. Designed from scratch in Altium Designer, the custom PCB serves as the central controller and power-distribution board, combining wireless communication, motor driving and on-board battery management. The project aims to replace loose jumper-wire prototyping with a robust, industrial-grade motherboard.

## Hardware architecture

### Controller and connectivity

The ESP32-WROOM-32D is the main controller, with a dual-core processor and a built-in PCB antenna. The project uses the Blynk IoT platform for low-latency Wi-Fi teleoperation over long distances through a custom smartphone interface with joysticks, buttons and status monitors.

### Power management and protection

- **2S Li-ion battery management:** on-board cell protection, implemented with the HY2120 IC and 8205A MOSFETs instead of an off-the-shelf module, for safe charge/discharge and deep-depletion protection.
- **Buck conversion:** a high-efficiency MP2307 converter steps the 2S battery input (approximately 7.4–8.4 V) down to a stable 3.3 V for logic components, avoiding the thermal issues associated with linear regulation.

### Motor drive and peripherals

- **DRV8833 dual motor driver:** drives two independent DC motors and includes thermal-shutdown and overcurrent protection, supporting operation under stalled-motor conditions.
- **Buzzer and LED headlights:** transistor-driven high-decibel warning and status peripherals for indication and night operation.

## PCB design approach

- Keep the ESP32 antenna area free of copper pours and traces, and separate analog/power sections from digital logic to reduce noise coupling and support signal integrity.
- Calculate and use wider traces and copper pours for high-current battery-to-motor-driver paths to reduce voltage drop and heat buildup.
- Use top- and bottom-layer ground pours with via stitching to provide short return paths and improve board stability.

## Firmware and control

The firmware is written in C++ using the Arduino IDE framework. The highly responsive Blynk smartphone interface provides remote control and status monitoring through joysticks, buttons and status indicators. Wi-Fi connectivity also supports potential remote-monitoring and internet-control use cases.

## Project visuals

Design visuals have not yet been added to this repository.

## About the designer

**Mert** — Electrical and Electronics Engineering student | Hardware Design Enthusiast

Designed with passion, driven by engineering principles.
