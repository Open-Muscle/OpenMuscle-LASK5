# LASK5 – A Gloveless Smart Glove Controller

![LASK5 Demo](https://img.shields.io/badge/Open%20Source-Yes-brightgreen)
![ESP32-S3](https://img.shields.io/badge/MCU-ESP32--S3-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

LASK5 is a compact, gloveless smart glove controller designed for robotics, machine learning, and human-computer interaction projects. Originally created to assist with labeling movement data for the [OpenMuscle](https://openmuscle.org) project, this controller is now a fully open-source interface capable of controlling robotic hands, LED sculptures, and more.

```markdown
📌 This device is part of the OpenMuscle ecosystem.  
For project-wide documentation, visit the [OpenMuscle Hub](https://github.com/Open-Muscle/OpenMuscle-Hub).
```

---

## 📽️ Watch the Demo

🎥 **YouTube Video:** [LASK5: The Gloveless Smart Glove](https://youtu.be/DJxaf0ww6us)

---

## 🔧 Features

- ESP32-S3 based (Wi-Fi + ESP-NOW enabled)
- 4-piston finger input with hall sensors
- Thumb joystick
- 128x32 OLED display for menus and feedback
- 4 SMD buttons for UI control
- Modular headers for add-ons (gyroscope, additional sensors)
- Written in MicroPython
- 3D-printable enclosure

---

## 🗂️ Repository Structure

### 🛠️ Hardware (KiCad)

You can find all historical and current KiCad hardware designs under:

📂 [`KiCad/`](https://github.com/Open-Muscle/OpenMuscle-LASK5/tree/main/KiCad)

Each folder contains complete KiCad files, BOMs, and version-specific layout changes.

| Version | Description | Folder |
|---------|-------------|--------|
| **v3.0** (Proposed) | New layout with joystick, button updates | [LASK_V3-0](https://github.com/Open-Muscle/OpenMuscle-LASK5/tree/main/KiCad/LASK_V3-0) |
| v2.0 | Button layout revision, early joystick test | [LASK_V2-0](https://github.com/Open-Muscle/OpenMuscle-LASK5/tree/main/KiCad/LASK_V2-0) |
| v1.1 | Original layout with 3-button config | [LASK_V1-1](https://github.com/Open-Muscle/OpenMuscle-LASK5/tree/main/KiCad/LASK_V1-1) |

🧩 Component footprints are stored in:
- [`ESP32WROOMfootprint`](https://github.com/Open-Muscle/OpenMuscle-LASK5/tree/main/KiCad/ESP32WROOMfootprint)
- [`USBfootprint`](https://github.com/Open-Muscle/OpenMuscle-LASK5/tree/main/KiCad/USBfootprint)
- [`ICM-42688-P`](https://github.com/Open-Muscle/OpenMuscle-LASK5/tree/main/KiCad/ICM-42688-P)

---

### 💾 Firmware

The firmware for all LASK versions is maintained centrally in:

📂 [OpenMuscle-Software → `/embedded/lask5`](https://github.com/Open-Muscle/OpenMuscle-Software/tree/main/embedded/lask5)

> ✅ Be sure to match the firmware branch or directory with your hardware version (see notes in the firmware repo for version compatibility).

---

## 🧠 Use Cases

- Robotic hand control (e.g. HiWonder, Arduino-powered systems)
- LED and kinetic art control
- Machine learning data labeling (OpenMuscle)
- Custom HCI devices, VR/AR control experiments

---

## 🚀 Getting Started

1. Visit the [OpenMuscle Hub](https://github.com/Open-Muscle/OpenMuscle-Hub) for device setup overview.
2. Select your hardware version from the `/KiCad` folder.
3. Follow included assembly instructions (or upcoming guides at [openmuscle.org](https://openmuscle.org)).
4. Flash your ESP32-S3 using the LASK5 firmware from [OpenMuscle-Software](https://github.com/Open-Muscle/OpenMuscle-Software).
5. Power on, test input, and begin using ESP-NOW or serial modes.

---

## 🤝 Contribute

We welcome PRs for hardware, firmware, or documentation.  
You can also submit ideas or questions in [OpenMuscle Discussions](https://github.com/Open-Muscle/OpenMuscle-Hub/discussions) (coming soon).

> If you build your own LASK5 device, let us know!  
> Tag [@OpenMuscle](https://github.com/Open-Muscle) or submit to the Community Builds section.

---

## 📜 License

This repository’s **KiCad files and mechanical designs** are licensed under the  
📄 [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

Any code snippets are licensed under the [MIT License](https://opensource.org/licenses/MIT).

```markdown
🔍 See [LICENSE.md](../LICENSE.md) for full licensing details.
```

---

Made with 💡 by [TURFPTAx](https://github.com/turfptax) for the OpenMuscle initiative.
