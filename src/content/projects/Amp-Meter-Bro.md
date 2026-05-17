---
title: "Amp Meter Bro: Smart Power Metering Device Prototype"
description: "An embedded smart metering prototype that measures voltage, current, and power in real time using an ESP32, INA219 current monitor, OLED display, and web dashboard."
pubDate: "May 9 2026"
heroImage: "/amp-meter-bro.jpeg"
badge: "Embedded"
github: "https://github.com/liuephram-commits/Amp-Meter-Bro/tree/nomi"
tags: ["Embedded Systems", "ESP32", "Power Electronics", "IoT"]
---

## Overview

Amp Meter Bro is a portable smart power metering device prototype designed to demonstrate the core ideas behind modern power monitoring systems. The project integrates embedded hardware, current sensing circuitry, local display feedback, and a web-based dashboard to monitor voltage, current, and power consumption in real time.

The prototype was presented at the **Modern Marvels Showcase** as an active hardware and embedded systems project.

## Motivation

As modern computing systems continue to grow, efficient and reliable power electronics have become increasingly important. Smart metering systems are widely used to measure, monitor, and respond to electrical conditions in practical applications.

This project was built to provide a hands-on demonstration of how smart metering devices work at a system level. Instead of working directly with high-voltage AC power, the current prototype uses a safer **9 V DC demonstration setup** with dummy loads to model normal and overcurrent operating conditions.

## System Design

The prototype uses an ESP32 microcontroller as the main control unit. A 9 V battery powers the demonstration system, while a DC/DC converter steps the voltage down to 5 V for the ESP32. The ESP32 communicates with the INA219 current monitor through I2C and displays real-time measurements on an OLED screen.

The system also includes LED status indicators and a web dashboard for monitoring measured data over time.

### Main Hardware Components

- ESP32 microcontroller
- INA219 current and voltage monitor
- OLED display
- LM2596 DC/DC converter
- 9 V battery supply
- Dummy load resistors for normal and overcurrent testing
- LED status indicators
- 3D-printed enclosure

## Key Features

### Real-Time Current and Power Monitoring

The INA219 sensor measures current and voltage through an I2C interface. The ESP32 processes this data to compute and display voltage, current, and power in real time.

The prototype uses known load resistance values, allowing measured data to be compared against expected electrical relationships for validation.

### Local OLED Display

The OLED display provides real-time feedback directly on the device, allowing users to view measured voltage, current, power, and operating status without needing a computer.

### Web Dashboard

The web dashboard is designed to visualize current and power data over time. Planned and active dashboard features include:

- Real-time voltage, current, and power display
- Overcurrent alarm status
- Adjustable current threshold
- Resettable timer/counter
- CSV data export

### Overcurrent Demonstration

The demonstration uses a switchable dummy load system with different resistance values to represent normal operation and overcurrent conditions. When current exceeds the selected threshold, the system updates the device status and triggers a visual warning through the LED indicator and dashboard.

## Technical Challenges

### Project Scope and Safety

Because the project was developed within a short design timeline, the first prototype was intentionally limited to a low-voltage **9 V DC** system. This allowed the team to focus on measurement, embedded control, and dashboard integration while keeping the demonstration safe and manageable.

Future versions may include front-end protection circuitry and higher-voltage measurement capability.

### Current Measurement Design

Several current sensing approaches were considered, including shunt-based sensing, Hall-effect sensing, and current transformer-based sensing. For this prototype, the team selected the INA219 because it provides current, voltage, and power measurement support through a well-documented I2C interface.

### Hardware Integration

The project required integrating the ESP32, INA219, OLED display, DC/DC converter, dummy loads, and enclosure into a compact prototype. The system also needed to support both local display feedback and wireless data visualization through the web dashboard.

## Team Contributions

### Nomi Wang

- Hardware design and implementation
- 3D-printed enclosure design for the device and dummy load
- Sensor calibration
- Overcurrent detection logic for firmware development

### Ephram Liu

- Web dashboard development
- ESP32-to-dashboard communication
- I2C communication between the sensor and OLED display
- Data processing and visualization

## Future Work

- Deploy the real-time data visualization website as a digital dashboard
- Add data tracking and logging functionality
- Scale the hardware design toward two-phase and three-phase power systems
- Add undercurrent detection in addition to overcurrent detection
- Design a custom PCB with integrated current sensing, DC/DC conversion, and microcontroller circuitry

## Project Documents

- [View Project Description PDF](/projects/amp-meter-bro-project-description.pdf)
- [View Modern Marvels Showcase Poster PDF](/projects/amp-meter-bro-modern-marvels-poster.pdf)

## Live Demo

This demo shows the current prototype measuring voltage, current, and power in real time. The device uses an ESP32 and INA219 current monitor to process measurements, displays live readings on the OLED screen, and updates the system status based on the selected load condition.

<video controls width="100%">
    <source src="/videos/amp-meter-bro-demo.mp4" type="video/mp4" />
    Your browser does not support the video tag.
</video>