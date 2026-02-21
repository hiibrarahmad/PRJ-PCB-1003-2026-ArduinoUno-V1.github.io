<div align="center">

<img src="https://raw.githubusercontent.com/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io/main/Assets/PRJ-2026-PCB-0001-UNO-variant1.jpg" width="100%" alt="Arduino UNO V1 — Top View"/>

---

# ⚡ PRJ-2026-PCB-0001-UNO-V1

### Custom Arduino UNO Compatible Development Board

**Designed by [Hibrar Ahmad](https://github.com/hiibrarahmad) · Powered by ATmega328P**

[![PCB Version](https://img.shields.io/badge/PCB%20Version-V1-00c8ff?style=for-the-badge)](#)
[![Layer Count](https://img.shields.io/badge/PCB%20Layers-2%20Layer-ff6b35?style=for-the-badge)](#)
[![MCU](https://img.shields.io/badge/MCU-ATmega328P-22c55e?style=for-the-badge)](#)
[![USB](https://img.shields.io/badge/USB-Type--C-a855f7?style=for-the-badge)](#)
[![Interface](https://img.shields.io/badge/Interface-CH340G-f59e0b?style=for-the-badge)](#)
[![Voltage](https://img.shields.io/badge/Logic-3.3V%20%2F%205V-0ea5e9?style=for-the-badge)](#)

[![License](https://img.shields.io/badge/License-Open%20Hardware-16a34a?style=for-the-badge)](#)
[![Last Commit](https://img.shields.io/github/last-commit/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io?style=for-the-badge&color=0891b2&label=Last%20Commit)](../../commits/main)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-22c55e?style=for-the-badge&logo=github)](https://hiibrarahmad.github.io/PRJ-2026-PCB-0001-UNO-V1.github.io/)
[![Visitors](https://visitor-badge.laobi.icu/badge?page_id=hiibrarahmad.PRJ-2026-PCB-0001-UNO-V1.github.io&style=for-the-badge&color=0e7490)](https://github.com/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io)

<br/>

[🔬 Interactive PCB View](https://hiibrarahmad.github.io/PRJ-2026-PCB-0001-UNO-V1.github.io/) · [📋 Project Assets](https://github.com/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io/tree/main/Assets) · [📜 BOM](#-bill-of-materials)

</div>

---

## 📖 Project Overview

**PRJ-2026-PCB-0001-UNO-V1** is a **custom-designed Arduino UNO compatible development board** built around the **ATmega328P** microcontroller. This board replaces the classic USB-B connector with a modern **USB Type-C** interface and uses the **CH340G** USB-to-serial bridge IC for reliable host communication — all while maintaining full compatibility with the standard Arduino UNO pinout and ecosystem.

> 💡 Designed with SMD components for a cleaner layout, onboard **3.3V and 5V** regulated power rails, dual crystal oscillators for USB and MCU clocking, and a fully Arduino UNO-compatible shield connector footprint.

---

## 🖼️ PCB Preview

<table>
<tr>
<td align="center" width="50%">

**🔝 Top Side**

<img src="https://raw.githubusercontent.com/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io/main/Assets/PRJ-2026-PCB-0001-UNO-variant1.jpg" width="100%" alt="UNO V1 PCB — Top View"/>

</td>
<td align="center" width="50%">

**🔻 Bottom Side**

<img src="https://raw.githubusercontent.com/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io/main/Assets/PRJ-2026-PCB-0001-UNO-variant1bot.jpg" width="100%" alt="UNO V1 PCB — Bottom View"/>

</td>
</tr>
</table>

<div align="center">

🔗 **[→ View Interactive PCB Online](https://hiibrarahmad.github.io/PRJ-2026-PCB-0001-UNO-V1.github.io/)**

</div>

---

## 🎯 Core Design Goals

| Goal | Specification |
|------|--------------|
| 🧠 **Microcontroller** | ATmega328P — Arduino UNO compatible |
| 🔌 **USB Interface** | USB Type-C (modern connector) via CH340G |
| ⚡ **Power Rails** | Onboard 3.3V (SOT223) + 5V (SOT223) regulation |
| 🕹️ **Arduino Pinout** | Full UNO shield connector compatibility |
| 🔧 **Programmability** | USB bootloader + ICSP 2×3 header |
| 💡 **Indicators** | Power, TX, RX, and User LED onboard |
| 📦 **Form Factor** | Standard Arduino UNO footprint |

---

## 🧠 System Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                      UNO V1 CARRIER BOARD                           │
│                                                                     │
│  ┌──────────┐    ┌────────────┐    ┌─────────────────────────────┐  │
│  │ USB TYPE-C│──▶│   CH340G   │───▶│      ATmega328P              │  │
│  └──────────┘    │ USB-Serial │    │   16 MHz Crystal (Y1)        │  │
│                  │ Bridge IC  │    │   14 Digital I/O             │  │
│                  │ 12 MHz (Y2)│    │   6 Analog Inputs (ADC)      │  │
│                  └────────────┘    │   6 PWM Outputs              │  │
│                                    └────────────┬────────────────┘  │
│  ┌──────────┐    ┌────────────┐                 │                   │
│  │ POWER    │───▶│  5V VREG   │─────────────────┤                   │
│  │ JACK J2  │    │  (U4 SOT223)│                │                   │
│  └──────────┘    └────────────┘    ┌────────────▼────────────────┐  │
│                  ┌────────────┐    │       3.3V VREG             │  │
│                  │  500mA F1  │    │      (U2 SOT223)            │  │
│                  │  Fuse      │    └─────────────────────────────┘  │
│                  └────────────┘                                     │
│                                                                     │
│  ┌─────── CONNECTORS ──────────────────────────────────────────┐   │
│  │  P1 ──▶ Arduino UNO Shield Header (Standard)               │   │
│  │  P2 ──▶ 3×2 ICSP SPI Programming Header                   │   │
│  │  J3 ──▶ USB Type-C Connector                               │   │
│  │  JP10b ──▶ Jumper Selector                                 │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                     │
│  ┌─────── INDICATORS ──────────────────────────────────────────┐   │
│  │  D1 ──▶ Yellow LED (Power)                                  │   │
│  │  D2, D3 ──▶ Red LEDs                                       │   │
│  │  D4, D5 ──▶ Green LEDs                                     │   │
│  │  D6 ──▶ Red LED (User/Status)                              │   │
│  └─────────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 💻 ATmega328P — Microcontroller

<table>
<tr><th>Category</th><th>Specification</th></tr>
<tr><td>🧮 <strong>Processor</strong></td><td>ATmega328P 8-bit AVR RISC @ 16 MHz</td></tr>
<tr><td>💾 <strong>Flash</strong></td><td>32 KB (2 KB used by bootloader)</td></tr>
<tr><td>🗃️ <strong>SRAM</strong></td><td>2 KB</td></tr>
<tr><td>📦 <strong>EEPROM</strong></td><td>1 KB</td></tr>
<tr><td>🔌 <strong>Digital I/O</strong></td><td>14 pins (6 with PWM output)</td></tr>
<tr><td>📡 <strong>Analog Inputs</strong></td><td>6 × 10-bit ADC channels</td></tr>
<tr><td>⚡ <strong>Operating Voltage</strong></td><td>5V</td></tr>
<tr><td>🔋 <strong>Input Voltage</strong></td><td>7–12V (recommended)</td></tr>
<tr><td>📶 <strong>DC Current per I/O</strong></td><td>20 mA (max 40 mA)</td></tr>
<tr><td>🔵 <strong>Serial</strong></td><td>UART, SPI, I2C</td></tr>
<tr><td>🕐 <strong>Crystal</strong></td><td>12 MHz SMD (Y1)</td></tr>
<tr><td>📐 <strong>Package</strong></td><td>TQFP-32 SMD</td></tr>
</table>

---

## 🔌 PCB Interface Map

### 🖥️ USB Interface
- **USB Type-C** connector (J3) → **CH340G** USB-to-Serial bridge (U3, SO16)
- **12 MHz Crystal (Y2)** for CH340G USB clock
- Supports auto-reset for Arduino bootloader upload

### ⚡ Power System
- **Power Jack (J2)** — DC barrel jack input (7–12V)
- **5V Regulator (U4)** — SOT223 package LDO
- **3.3V Regulator (U2)** — SOT223 package LDO
- **Fuse F1 (500mA)** — USB power protection
- **Fuse F2 (500mA)** — Main rail protection
- **Fuse F3 (3A)** — Barrel jack input protection
- **Fuse F4 (0.5A)** — Secondary rail protection

### 🧠 Microcontroller & Programming
- **ATmega328P (U1)** — TQFP SMD package
- **16 MHz Crystal (Y1)** — MCU clock
- **ICSP Header (P2)** — 3×2 SPI programming header for direct flashing
- **Reset Button (S1)** — Tactile SMD push button

### 🔗 Shield Connectivity
- **P1** → Standard **Arduino UNO** shield connector (digital, analog, power, ICSP pins)
- Fully compatible with all standard Arduino UNO shields

### 💡 LED Indicators
- **D1 (Yellow)** — Power indicator
- **D2, D3 (Red)** — TX/RX communication indicators
- **D4, D5 (Green)** — Status / user LEDs
- **D6 (Red)** — User-programmable LED (Pin 13)

### 🔧 Jumper
- **JP10b** — Boot/mode selection jumper

---

## 📋 Bill of Materials

| References | Value | Footprint | Qty |
|-----------|-------|-----------|-----|
| C1, C2, C3, C4, C11, C16, C17 | 100n | CAP 0805/2012 | 7 |
| C7, C8, C20, C21 | 100n | CAP 1206/3216 | 4 |
| C12, C13, C14, C15 | 22p | CAP 0805/2012 | 4 |
| C5, C10, C18 | 10u | SMT_C_Tantalum_A | 3 |
| C6, C19 | 22u | SMT_C_Tantalum_A | 2 |
| C9 | 10n | CAP 0805/2012 | 1 |
| R2, R3, R11 | 1k | RES 0805 (2012X06L) | 3 |
| R1, R4 | 10K | RES 0805 (2012X06L) | 2 |
| R5, R6 | 680 | RES 0805 (2012X06L) | 2 |
| R8, R9 | 4.7K | RES 0805 (2012X06L) | 2 |
| R10, R12 | 1.8k | RES 0805 (2012X06L) | 2 |
| R7 | 220Ω | RES 0805 (2012X06L) | 1 |
| R13 | 680Ω | RES 0805 (2012X06L) | 1 |
| L1 | 100u | IND0805 | 1 |
| D2, D3 | RED | LED 0805/2012 RED | 2 |
| D4, D5 | Green | LED 0805/2012 GREEN | 2 |
| D1 | Yellow | LED 0805/2012 YELLOW | 1 |
| D6 | Red | LED 0805/2012 RED | 1 |
| U1 | ATmega328P | ATMEGA328P | 1 |
| U2 | 3.3V | SOT223_M | 1 |
| U3 | CH340G | SO16_M | 1 |
| U4 | 5V | SOT223_M | 1 |
| Y1, Y2 | 12M | Crystal SMD | 2 |
| F1, F4 | 0.5A | 1206_F2 | 2 |
| F2 | 500m | 1206_F1 | 1 |
| F3 | 3A | 1206_F1 | 1 |
| JP10b | jumper selector | jumper selector | 1 |
| S1 | PB | SW_PB_SMD_2PIN_SPST_6X3X2 | 1 |
| J2 | Female | Power Jack BIG | 1 |
| J3 | 12b | HRO_TYPE-C-31-M-12 - Extended | 1 |
| P1 | UNO | ARDUINO_UNO_CONNECTOR | 1 |
| P2 | 3x2 | IDC_2X3 | 1 |

---

## 📐 PCB Specifications

<table>
<tr><th>Parameter</th><th>Value</th></tr>
<tr><td>PCB Version</td><td>V1</td></tr>
<tr><td>PCB Definition</td><td>Development Board</td></tr>
<tr><td>Board Thickness</td><td>1.6 mm</td></tr>
<tr><td>Layer Count</td><td>2 Layers</td></tr>
<tr><td>Material</td><td>FR4</td></tr>
<tr><td>Surface Finish</td><td>HASL / ENIG</td></tr>
<tr><td>Solder Mask</td><td>Top & Bottom · Color: Green</td></tr>
<tr><td>Silkscreen</td><td>Top & Bottom · Color: White</td></tr>
<tr><td>RoHS</td><td>✅ Compliant</td></tr>
</table>

---

## 🛠️ Software & Development

| Component | Details |
|-----------|---------|
| IDE | Arduino IDE 1.x / 2.x |
| Board Profile | Arduino UNO (ATmega328P) |
| Bootloader | Optiboot / Arduino UNO Bootloader |
| USB Driver | CH340G (CH341SER) |
| Clock Speed | 16 MHz |
| Programmer | USB via CH340G or ICSP |
| Voltage | 5V logic |

---

## 🚀 Getting Started

1. **Install CH340G driver** — Download from [WCH official site](http://www.wch.cn/products/CH340.html) for your OS
2. **Connect via USB Type-C** cable
3. **Open Arduino IDE** and select `Board: Arduino UNO`
4. **Select the correct COM port** assigned to CH340G
5. **Upload your sketch** — the board auto-resets for programming

---

## 📁 Repository Structure

```
PRJ-2026-PCB-0001-UNO-V1.github.io/
│
├── Assets/
│   ├── PRJ-2026-PCB-0001-UNO-variant1.jpg       ← Top view (JPG)
│   └── PRJ-2026-PCB-0001-UNO-variant1bot.jpg    ← Bottom view (JPG)
│
├── index.html                                    ← Interactive PCB viewer
├── .gitattributes
└── README.md                                     ← This file
```

---

## 🔗 Links

| Resource | URL |
|----------|-----|
| 🌐 Interactive PCB View | [hiibrarahmad.github.io/PRJ-2026-PCB-0001-UNO-V1.github.io](https://hiibrarahmad.github.io/PRJ-2026-PCB-0001-UNO-V1.github.io/) |
| 👤 Designer | [github.com/hiibrarahmad](https://github.com/hiibrarahmad) |
| 📦 Top View | [Assets/PRJ-2026-PCB-0001-UNO-variant1.jpg](https://github.com/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io/blob/main/Assets/PRJ-2026-PCB-0001-UNO-variant1.jpg) |
| 📦 Bottom View | [Assets/PRJ-2026-PCB-0001-UNO-variant1bot.jpg](https://github.com/hiibrarahmad/PRJ-2026-PCB-0001-UNO-V1.github.io/blob/main/Assets/PRJ-2026-PCB-0001-UNO-variant1bot.jpg) |

---

<div align="center">

**PRJ-2026-PCB-0001-UNO-V1**

*Custom Arduino UNO Compatible Board · Designed by Hibrar Ahmad*

[![Platform](https://img.shields.io/badge/Platform-ATmega328P-ef4444?style=for-the-badge)](#)
[![USB](https://img.shields.io/badge/USB-Type--C-a855f7?style=for-the-badge)](#)
[![Compatible](https://img.shields.io/badge/Compatible-Arduino%20UNO-00c8ff?style=for-the-badge)](#)

© 2026 Hibrar Ahmad. All Rights Reserved.

</div>
