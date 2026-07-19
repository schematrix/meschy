# Meschy

An open-source LoRa development board for Meshtastic and long-range wireless communication.

Meschy is an open-source hardware platform built around the Nordic nRF52840 microcontroller and the Semtech SX1262 LoRa transceiver. It is designed for reliable, low-power, long-range communication and is fully compatible with the Meshtastic ecosystem.

Whether you're building an off-grid messaging device, an IoT sensor network, or experimenting with mesh communications, Meschy provides a compact and flexible hardware platform.

---

## Features

* Nordic nRF52840 MCU
* Semtech SX1262 LoRa Transceiver
* Bluetooth Low Energy (BLE 5.0)
* USB Type-C interface
* Low-power design
* Meshtastic compatible
* Expansion GPIOs
* Open-source hardware

---

## Getting Started: Installing Meshtastic Firmware

Once you have an assembled Meschy board in hand, here's how to get it running on the Meshtastic network.

### 1. Put the board into bootloader mode

The nRF52840 uses a **UF2 bootloader**, which is different from the flashing process used on ESP32-based Meshtastic devices (no `esptool` or serial flashing needed here). To enter bootloader mode:

1. Connect Meschy to your computer via USB-C.
2. **Double-tap the reset button** quickly.
3. The board will reboot into bootloader mode and appear on your computer as a USB mass storage drive (usually named something like `MESCHYBOOT` or `NRF52BOOT`).

If double-tapping doesn't work on the first try, it can take a couple of attempts to get the timing right.

### 2. Flash the Meshtastic firmware

1. Download the latest **nRF52-compatible** `.uf2` firmware build for your device from the official [Meshtastic firmware releases](https://github.com/meshtastic/firmware/releases) page.
   * Since Meschy is based on the MiniX hardware design, start with the MiniX (or closest matching nRF52840/SX1262) variant build. If a dedicated Meschy build isn't available yet, this is the recommended starting point.
2. Drag and drop the `.uf2` file onto the USB drive that appeared in Step 1.
3. The board will automatically flash the firmware and reboot on its own. The USB drive will disappear once flashing is complete — this is normal.

> Alternatively, you can use the [Meshtastic Web Flasher](https://flasher.meshtastic.org/) for supported boards. Note that nRF52-based boards generally rely on the drag-and-drop UF2 method above rather than Web Serial/WebUSB flashing used by ESP32 boards.

### 3. Configure the device

After flashing, Meschy will show up as a Bluetooth Low Energy device. Configure it using any official Meshtastic client:

* **Meshtastic Android app** ([Google Play](https://play.google.com/store/apps/details?id=com.geeksville.mesh))
* **Meshtastic iOS app** ([App Store](https://apps.apple.com/us/app/meshtastic/id1586432531))
* **Meshtastic Web Client** ([client.meshtastic.org](https://client.meshtastic.org/)) — connect via BLE or USB serial
* **Meshtastic CLI** (Python) for advanced/scripted configuration

Pair with the device over Bluetooth, then set your region (LoRa frequency plan), device role, and channel/encryption settings according to the [official Meshtastic documentation](https://meshtastic.org/docs/).

### 4. Updating firmware later

To update firmware in the future, repeat Step 1 (double-tap reset to re-enter bootloader mode) and drag the new `.uf2` file onto the drive. Your radio/channel settings are generally preserved across firmware updates, but it's good practice to back up your configuration first via the app (Settings → Export Configuration).

### Troubleshooting

* **Board doesn't show up as a drive:** Try a different USB-C cable (some are power-only) and a different USB port.
* **Double-tap isn't registering:** Try tapping slightly faster/slower, or hold reset briefly before releasing.
* **Device not visible over Bluetooth after flashing:** Give it 10–15 seconds after reboot, and make sure Bluetooth is enabled on your phone/computer.

---

## Design Origin

Meschy is based on the open-source Meshtastic **MiniX** hardware design.

Rather than being a direct copy, this project is a customized hardware variant that has undergone substantial hardware redesigns to better fit our engineering goals and manufacturing requirements.

Major modifications include:

* Redesigned power supply circuitry
* Completely revised button circuitry
* PCB layout optimization
* Improved component selection
* Routing refinements
* Manufacturing optimizations
* General hardware improvements for production

These changes were made to improve reliability, manufacturability, and long-term maintainability while preserving compatibility with the Meshtastic ecosystem.

We sincerely thank the original MiniX designers and the Meshtastic community for making open hardware possible.

---

## Project History

This project was originally developed under the name **ULAQ**.

During development, we discovered a trademark conflict with an existing registered brand. To avoid legal issues and respect intellectual property rights, the project was officially renamed to **Meschy**.

Since the hardware had already reached the manufacturing stage, the current PCB revision still contains the "ULAQ" silkscreen on the board. This is purely cosmetic and does not indicate a different hardware version.

Please note:

* ULAQ and Meschy are the same hardware project.
* The PCB may still display the ULAQ name.
* All future documentation, software, and hardware revisions will use the Meschy name.

---

## Repository Structure

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

## Manufacturing Files

This repository includes everything required to manufacture and assemble the board.

### Gerber Files
`meschy_gerber.zip`

Contains the complete PCB manufacturing package, including:

* Copper layers
* Solder mask
* Silkscreen
* Drill files
* Board outline

Compatible with virtually all PCB manufacturers, including:

* JLCPCB
* PCBWay
* Seeed Fusion
* OSH Park
* Any Gerber-compatible fabrication service

### Bill of Materials (BOM)
`MESCHY_BOM.xlsx`

Complete component list required to assemble the board.

### Pick & Place
`MESCHY_PICK_AND_PLACE.xlsx`

Automated SMT assembly coordinates.

### Schematic
`MESCHY_SCH.pdf`

Complete circuit schematic for reference and development.

### 3D Model
`3D_PCB.step`

STEP model for enclosure design and mechanical integration.

### PCB Images
`PCB_PICS.pdf`

Reference photographs of the manufactured PCB.

---

## Applications

Meschy can be used for:

* Meshtastic devices
* Off-grid communication
* Emergency communication
* GPS tracking
* IoT sensor networks
* Outdoor adventures
* Remote telemetry
* Educational and research projects

---

## Open Hardware

Meschy is released as an open hardware project to encourage learning, experimentation, and community-driven development.

Contributions, bug reports, hardware improvements, and pull requests are always welcome.

---

## License

This repository contains open-source hardware design files. Please respect the applicable open-source license and the trademarks of third parties.

---

## Notes

The first production revision of the PCB still contains the ULAQ silkscreen due to the project's original name. Only the project name has changed. The hardware, documentation, Gerber files, BOM, and all future development belong to the Meschy project.
