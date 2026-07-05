# Meschy

<p align="center">
  <b>An open-source LoRa development board for Meshtastic and long-range wireless communication.</b>
</p>

Meschy is an open-source hardware platform built around the **Nordic nRF52840** microcontroller and the **Semtech SX1262** LoRa transceiver. It is designed for reliable, low-power, long-range communication and is fully compatible with the Meshtastic ecosystem.

Whether you're building an off-grid messaging device, an IoT sensor network, or experimenting with mesh communications, Meschy provides a compact and flexible hardware platform.

---

# Features

- Nordic nRF52840 MCU
- Semtech SX1262 LoRa Transceiver
- Bluetooth Low Energy (BLE 5.0)
- USB Type-C interface
- Low-power design
- Meshtastic compatible
- Expansion GPIOs
- Open-source hardware

---

# Design Origin

Meschy is based on the open-source **Meshtastic MiniX** hardware design.

Rather than being a direct copy, this project is a customized hardware variant that has undergone substantial hardware redesigns to better fit our engineering goals and manufacturing requirements.

Major modifications include:

- Redesigned power supply circuitry
- Completely revised button circuitry
- PCB layout optimization
- Improved component selection
- Routing refinements
- Manufacturing optimizations
- General hardware improvements for production

These changes were made to improve reliability, manufacturability, and long-term maintainability while preserving compatibility with the Meshtastic ecosystem.

We sincerely thank the original MiniX designers and the Meshtastic community for making open hardware possible.

---

# Project History

This project was originally developed under the name **ULAQ**.

During development, we discovered a **trademark conflict** with an existing registered brand. To avoid legal issues and respect intellectual property rights, the project was officially renamed to **Meschy**.

Since the hardware had already reached the manufacturing stage, the current PCB revision still contains the **"ULAQ"** silkscreen on the board.

This is purely cosmetic and **does not indicate a different hardware version**.

Please note:

- **ULAQ and Meschy are the same hardware project.**
- The PCB may still display the **ULAQ** name.
- All future documentation, software, and hardware revisions will use the **Meschy** name.

---

# Repository Structure

```
Hardware/
├── 3D_PCB.step
├── PCB_PICS.pdf
├── MESCHY_BOM.xlsx
├── MESCHY_PICK_AND_PLACE.xlsx
├── MESCHY_SCH.pdf
└── meschy_gerber.zip
```

---

# Manufacturing Files

This repository includes everything required to manufacture and assemble the board.

## Gerber Files

`meschy_gerber.zip`

Contains the complete PCB manufacturing package, including:

- Copper layers
- Solder mask
- Silkscreen
- Drill files
- Board outline

Compatible with virtually all PCB manufacturers, including:

- JLCPCB
- PCBWay
- Seeed Fusion
- OSH Park
- Any Gerber-compatible fabrication service

---

## Bill of Materials (BOM)

`MESCHY_BOM.xlsx`

Complete component list required to assemble the board.

---

## Pick & Place

`MESCHY_PICK_AND_PLACE.xlsx`

Automated SMT assembly coordinates.

---

## Schematic

`MESCHY_SCH.pdf`

Complete circuit schematic for reference and development.

---

## 3D Model

`3D_PCB.step`

STEP model for enclosure design and mechanical integration.

---

## PCB Images

`PCB_PICS.pdf`

Reference photographs of the manufactured PCB.

---

# Applications

Meschy can be used for:

- Meshtastic devices
- Off-grid communication
- Emergency communication
- GPS tracking
- IoT sensor networks
- Outdoor adventures
- Remote telemetry
- Educational and research projects

---

# Open Hardware

Meschy is released as an open hardware project to encourage learning, experimentation, and community-driven development.

Contributions, bug reports, hardware improvements, and pull requests are always welcome.

---

# License

This repository contains open-source hardware design files.

Please respect the applicable open-source license and the trademarks of third parties.

---

# Notes

The first production revision of the PCB still contains the **ULAQ** silkscreen due to the project's original name.

Only the project name has changed.

The hardware, documentation, Gerber files, BOM, and all future development belong to the **Meschy** project.
