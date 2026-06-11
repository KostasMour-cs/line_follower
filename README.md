# Line Follower Robot

An autonomous line-following robot built around the RP2040 microcontroller and a custom infrared sensor array. The project features a high-performance control system with a custom PID controller and low-pass filtering, enabling fast, stable, and precise line tracking. Developed in C++ using the Arduino framework as part of an Embedded Systems course project.

## Overview

This project was developed for the **Embedded Systems** course (Group 1 – Section 1). The goal was to design and implement an autonomous robotic vehicle capable of following a black line on a white surface in real time. The robot uses multiple IR sensors to detect its position relative to the track and continuously adjusts motor speeds through a custom control algorithm.

### Key Features

* Autonomous line tracking using IR sensors
* Custom PID controller implemented from scratch
* Low-pass filtering for improved sensor stability
* Real-time motor speed and direction control
* Multiple operating modes (Turbo and Stable)
* Optimized for fast and accurate path following
* No external control libraries used

## Hardware Components

| Component       | Description                          |
| --------------- | ------------------------------------ |
| Microcontroller | RP2040 (Raspberry Pi Pico)           |
| Sensors         | 5-Channel Infrared (IR) Sensor Array |
| Motors          | 2× N20 500 RPM DC Geared Motors      |
| Motor Driver    | Integrated on the control board      |
| Power Supply    | 3.7V Li-Po Battery                   |
| Chassis/Board   | Breadboard / Custom BrashBoard       |

## Software & Development Tools

* **Language:** C++
* **Framework:** Arduino Framework
* **IDE:** Arduino IDE / VS Code with PlatformIO
* **Core Library:** Arduino.h
* **External Libraries:** None

All control algorithms, including the PID controller and signal filtering mechanisms, were implemented from scratch to maximize performance and provide a deeper understanding of embedded control systems.

## Pin Configuration

| Component        | RP2040 Pin | Type            | Description                                       |
| ---------------- | ---------- | --------------- | ------------------------------------------------- |
| Left Motor PWM   | GP8        | Output          | PWM speed control for left motor                  |
| Left Motor DIR   | GP9        | Output          | Direction control (LOW = Forward, HIGH = Reverse) |
| Right Motor PWM  | GP10       | Output          | PWM speed control for right motor                 |
| Right Motor DIR  | GP11       | Output          | Direction control (LOW = Forward, HIGH = Reverse) |
| Digital IR Left  | GP0        | Input           | Extreme left line detection                       |
| Digital IR Right | GP1        | Input           | Extreme right line detection                      |
| Analog IR Left   | GP27 (A1)  | Input           | Left sensor reading                               |
| Analog IR Center | GP26 (A0)  | Input           | Center sensor reading                             |
| Analog IR Right  | GP28 (A2)  | Input           | Right sensor reading                              |
| Button 1         | GP20       | Input (Pull-up) | Calibration + Track 1 (Turbo Mode)                |
| Button 2         | GP21       | Input (Pull-up) | Calibration + Track 2/3 (Stable Mode)             |

## Control System

The robot determines its lateral position using the IR sensor array and computes a tracking error relative to the center of the line. A custom PID controller calculates corrective motor commands, while a low-pass filter reduces sensor noise and improves control stability. This combination allows the robot to maintain accurate tracking even at higher speeds.

## Results

The final system achieved reliable and responsive line following with smooth corner handling, minimal oscillations, and stable performance across multiple track layouts.
