# Custom RC Car PCB Design

> An engineering project focused on developing a dedicated, high-performance printed circuit board (PCB) for a 2WD remote-controlled vehicle. 

## Project Overview
This project involves the end-to-end design of a custom electronics platform for an RC car. Designed from scratch in Altium Designer, the goal is to create a centralized motherboard that handles power distribution, wireless communication, and motor driving. This approach eliminates messy wiring, optimizes power delivery, and provides a robust hardware foundation.

## Hardware Architecture & Components
The system architecture is divided into carefully integrated functional blocks:

- **Microcontroller:** ESP32 (Selected for dual-core processing and integrated wireless capabilities).
- **Motor Driver:** DRV8833 Dual Motor Driver (Driving 2 DC motors efficiently).
- **Power System:** 2S Li-Ion Battery configuration.
- **Power Management:** - Integrated Battery Management System (BMS) for safe charging and discharging.
  - On-board Buck Converter to step down the 2S voltage efficiently for the logic level components.
- **Peripherals:** Integrated Buzzer and LED circuits for status indication and feedback.

## Applied PCB Design Techniques
The board is being developed with professional PCB layout principles in Altium Designer:

- **Power Routing:** High-current trace width calculations for the 2S battery input and DRV8833 motor outputs to prevent thermal issues.
- **Switching Power Layout:** Optimized placement and routing for the Buck Converter to minimize EMI and ensure stable voltage drops.
- **Grounding Strategy:** Continuous copper ground planes (GND) to provide short return paths and improve overall signal integrity.
- **Component Placement:** Strategic grouping of power, logic, and motor driving sections to prevent noise coupling into the ESP32.
