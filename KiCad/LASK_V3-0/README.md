# LASK v3 – OpenMuscle Labeler PCB

**Version:** 3.0  
**KiCad Version:** 9.0.1  
**Project Type:** Embedded hardware (ESP32-based controller)  
**Use Case:** Labeling hand movement data for prosthetic machine learning models

This is the third iteration of the LASK (Labeler for Sensor Kit) PCB, designed as part of the OpenMuscle project. LASK v3 is a handheld device used to interact with muscle sensors, label data, and provide haptic and motion feedback during training sessions.

---

## 🧠 Major Additions in v3

- ✅ Added **haptic motor driver** with flyback diode protection  
- ✅ Added **ICM-42688-P IMU** (I²C, with alternate support for SPI)  
- ✅ Enhanced **power management** using a push-button latch and USB auto-power-on  
- ✅ Clean GPIO assignments for consistent firmware development

---

## 🧩 System Overview

| Subsystem           | Description |
|--------------------|-------------|
| **MCU**            | ESP32-S3-WROOM-1 (16MB flash, 8MB PSRAM) |
| **Sensors**        | 4x Hall effect sensors w/ 100nF capacitors to ground |
| **IMU**            | ICM-42688-P (I²C: GPIO8=SDA, GPIO9=SCL) |
| **Display**        | SSD1306 OLED (I²C shared) |
| **Input**          | 2 buttons (Menu & Select), Thumb joystick w/ push |
| **Output**         | Haptic motor driven via MOSFET on GPIO17 |
| **Power**          | MAX16054 latch, TPS7A0333 LDO, LTC4054 charger |
| **Interface**      | USB-C for charging and programming |

---

## 🧷 GPIO Pinout

| Function                | GPIO |
|------------------------|------|
| Hall Sensor 0          | 1    |
| Hall Sensor 1          | 2    |
| Hall Sensor 2          | 3    |
| Hall Sensor 3          | 4    |
| Joystick X             | 5    |
| Joystick Y             | 6    |
| Joystick Switch        | 7    |
| I²C SDA (IMU + OLED)   | 8    |
| I²C SCL (IMU + OLED)   | 9    |
| Select Button          | 10   |
| SPI MISO               | 11   |
| SPI SCK                | 12   |
| SPI MOSI               | 13   |
| Haptic Motor Signal    | 17   |
| Battery Voltage ADC    | 18   |
| Menu Button            | 21   |
| SPI CS (available)     | 22   |

---

## 🔋 Power Management

- **Charging:** LTC4054 linear charger via USB-C  
- **Voltage Regulation:** TPS7A0333 LDO with EN pin control  
- **Power-on Logic:** MAX16054 handles push-button latching  
  - **VBUS detection** auto-enables LDO via diode OR circuit  
  - Power can also be toggled with push button  
- **Haptic Driver:** IRLML2060 N-MOSFET, protected by 1N4007 diode

---

## 🛠️ Schematic

![LASK v3 Schematic](docs/lask_v3_schematic.png)  
> 📁 Located in `/kicad_project/`

---

## 🧪 Development Notes

- Future version may migrate IMU to SPI for better performance
- USB VBUS is sensed to allow automatic boot when plugged in
- Add decoupling capacitors on IMU pins for improved stability (see TODO in schematic)

---

## 📂 Repository Structure

```
/
├── kicad_project/
│ ├── LASKS-V3_0.kicad_sch
│ └── LASKS-V3_0.kicad_pcb
├── docs/
│ └── lask_v3_schematic.png
├── README.md
```

---

## 🔓 License

Open-source under [CERN-OHL-W v2](https://ohwr.org/project/cernohl/wikis/CERN-OHL-version-2)  
Part of the [OpenMuscle Project](https://openmuscle.org)
