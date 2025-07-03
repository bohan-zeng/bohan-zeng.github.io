---
layout: post
title: "🚀 Smart IR-Based AI Air Conditioner Controller — My First Step"
date: 2025-07-02 23:57:00 -0600
categories: [IoT, AI, Hardware, Project Log]
tags: [ESP32, IR, AC, Smart Home, PlatformIO, AI, Edge Computing]
---

This entry marks the beginning of my journey into building an End-to-End (E2E) edge AI agent to control an AC unit. It outlines my initial requirements and the foundational steps I've completed so far.

## 1. My Requirements

My core objectives for this project are clear:

* First, I aim to build an **E2E edge AI agent** capable of controlling a TECO split‑type AC via IR signals.
* Second, I want to ensure it supports both **Manual Smart Control** (which I envision implementing through a future app or voice interface) and an **Autonomous AI Mode** that will react based on sensor data.
* Finally, I'm starting with the **ESP32 DevKitC (WROOM)** as my initial IR bridge, keeping in mind future scalability for a more robust backend AI system and broader smart home integration.

## 2. Steps I've Completed

I've made significant strides in laying the groundwork for this ambitious project, tackling the essential setup phases.

### ✅ Hardware Setup

My journey began with selecting and acquiring the necessary hardware components. I decided on the **HX1838 IR Receiver + Emitter Kit** for its ease of use and availability, and I've successfully purchased two of these kits to have a backup. For the brain of the operation, I chose the **ESP32 DevKitC** as my primary development board, confident in its robust Wi-Fi and Bluetooth capabilities for future smart features. To facilitate prototyping, I also picked up a **breadboard**, a comprehensive **jumper wire set**, and a reliable **5 V 1 A USB adapter** along with a **data-capable micro-USB cable** for both power and programming.

### ✅ Wiring

With the hardware in hand, the next phase was to establish the basic connections. I carefully wired the HX1838 IR Receiver: connecting its VCC to the ESP32's 5 V (or 3.3 V) pin, GND to the ESP32's GND, and the OUT pin to ESP32's GPIO 5. I meticulously verified the breadboard setup, double-checking all connections to ensure they were secure and correct before powering anything on.

### ✅ Development Environment Setup

A robust development environment is absolutely key to efficient progress, and I'm pleased to say I've got mine set up. I successfully installed **VS Code** and the **PlatformIO IDE extension**, which I've found provides an excellent integrated development experience for embedded systems. Within PlatformIO, I created a new project, specifically targeting the **ESP32 Dev Module** and utilizing the **Arduino framework** to simplify programming the ESP32. To confirm everything was working, I compiled and uploaded a simple “Blink + Serial print” sketch. The upload process was a success, as you can see in the terminal output below, completing in a swift **46.10 seconds** and writing **269488 bytes**.

![Successful PlatformIO sketch upload to ESP32](/assets/images/first_upload.png)
*Figure 1: Successful PlatformIO sketch upload to ESP32.*

### ✅ Serial Monitor

Understanding the device's output is critical for debugging and verification, so I made sure to familiarize myself thoroughly with the Serial Monitor. I learned to open and effectively use the **PlatformIO Serial Monitor** (easily accessed via the 🔌 plug icon in VS Code). Through it, I confirmed the **LED blink** functionality and happily observed the serial prints, which correctly displayed “LED ON/OFF” every second, clearly indicating successful program execution. I also made sure to learn how to gracefully close the Serial Monitor using Ctrl+C or the trash icon, which is important for preventing frustrating port conflicts down the line.

![LED ON/OFF Serial Output](/assets/images/led_on_off.png)
*Figure 2: Serial Monitor output showing alternating "LED ON" and "LED OFF" messages.*

## 3. My Next Planned Step

My immediate focus is to prepare for the crucial IR testing phase with the HX1838. This involves a few key steps:

1.  First, I'll **install** the `IRremoteESP8266` library within my PlatformIO project, as this library is absolutely essential for handling IR communication.
2.  Next, I'll **replace** my current blinking sketch with a dedicated IR receive/replay sketch.
3.  Finally, I'll utilize the Serial Monitor to **capture TECO remote codes** from my air conditioner's remote and then **test the replay** of these captured codes back to the AC unit to verify that I can indeed control it.