---
title: "Interactive Synthetic Jet Actuator Display"
description: "A research and outreach hardware project demonstrating synthetic jet behavior through real-time actuation control, flow visualization, and an interactive ESP32-based control system."
pubDate: "Jun 10 2025"
heroImage: "/vortexrings.png"
badge: "Research"
github: ""
tags: ["Fluid Dynamics", "Embedded Systems", "ESP32", "Flow Visualization"]
---

## Overview

This project is an interactive synthetic jet actuator display designed to demonstrate how controlled fluid motion can be generated without net mass injection. The system allows users to adjust actuation frequency in real time and observe how synthetic jet behavior changes through flow visualization.

The project was presented at the **2025 College of Engineering Research Open House**, where it received the **Undergraduate Departmental Award under the Mechanical Engineering Division** and **Third Place in the People’s Choice Award**.

## Motivation

Synthetic jets are useful in engineering applications because they can generate controlled fluid motion without requiring a continuous external fluid supply. One example application is vortex-based propulsion for microrobots used in targeted drug delivery, where controlled flow structures can help small robotic systems navigate confined biological environments.

This project was also designed as an educational outreach tool. By allowing users to directly change the actuation frequency and observe the resulting flow behavior, the display makes fluid mechanics concepts more accessible to students and the general public.

## System Design

The system combines embedded control, actuation hardware, and optical flow visualization.

### Hardware Components

- ESP32 microcontroller
- Rotary encoder for frequency adjustment
- Push button for actuator on/off control
- LCD display for real-time frequency feedback
- Power amplifier
- Voice coil actuator
- Laser and cylindrical lens for flow visualization

### Actuator Mechanism

The actuator consists of a sealed cavity with an orifice on one side and a flexible membrane on the opposite side. The ESP32 generates a sinusoidal control signal that drives the actuator through an amplifier. As the membrane vibrates, it creates cyclic suction and expulsion of water through the orifice.

At certain actuation frequencies, this motion forms vortex-ring structures characteristic of synthetic jets.

## Technical Challenges

### Rotary Encoder Synchronization

Early testing showed unstable frequency changes because each rotary encoder detent produced multiple fast edge transitions. Mechanical bounce also introduced unwanted signals, causing the initial polling routine to miss or duplicate pulses.

To solve this, the control logic was improved using a quadrature state-machine approach, allowing the system to more reliably track encoder direction and frequency changes.

### Flow Visualization

Standard LEDs did not provide enough intensity to clearly visualize particle motion in water. To improve visibility, the system used a green laser paired with a cylindrical lens to create a laser sheet. This illuminated neutrally buoyant particles and made the synthetic jet structures easier to observe.

## Results

Testing across actuation frequencies from **1 Hz to 20 Hz** showed frequency-dependent flow behavior. The clearest and most defined vortex-ring structures were observed around **5 Hz**.

Although the small scale of the actuator limited visual clarity, the system successfully demonstrated how actuation frequency affects synthetic jet formation and flow structure.

## Project Documents

- [View Full Project Overview PDF](/projects/synthetic-jet-actuator-overview.pdf)
- [View Research Open House Poster PDF](/projects/synthetic-jet-actuator-poster.pdf)