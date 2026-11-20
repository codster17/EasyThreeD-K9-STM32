# Marlin 2 for EasyThreeD K9 — ET4000+ Board

An independent firmware development project to port **Marlin 2** to the EasyThreeD K9 3D printer equipped with the **ET4000+ control board**.

This repository contains the firmware source and configuration for the K9 ET4000+ hardware variant.

> **Firmware testing:** Please try the provided `mksLite.bin` firmware and report any problems, unexpected behavior, or compatibility issues.

## Hardware and development background

The EasyThreeD K9 uses a different front-panel and button arrangement from some other EasyThreeD printer models. This project documents those connections and adapts the firmware accordingly.

For original board photographs, hardware discussion, and development background, see:

- [Upstream development discussion — Issue #10](https://github.com/schmttc/EasyThreeD-K7-STM32/issues/10)

## Physical pin connections

The following tables document the physical connections identified for the K9 ET4000+ board.

### Connector numbering conventions

- **EXP1:** Pin numbers follow the numbering convention documented in the `Additional-Files` branch.
- **Other connectors:** Pin numbers are viewed from the rear and bottom of the printer, numbered from left to right and top to bottom.
- EXP1 pins **2, 4, 9, and 10** are not connected to any peripherals.

### 1. Main front button

The main front-panel button and LED connect through the EXP1 connector.

| Physical pin | EXP1 pin | Role | MCU pin |
|---:|---:|---|---|
| 1 | 11 | GND | GND |
| 2 | 12 | LED+ (connected to 3.3 V) | VDDA |
| 3 | 14 | LED− | PD2 |
| 4 | 13 | Switch (SW) | PA10 |

### 2. Front leveling buttons

The four front leveling buttons connect through the Wi-Fi connector.

| Physical pin | Wi-Fi pin | Role | Notes |
|---:|---:|---|---|
| 1 | 1 (EXP1_11) | GND | Common for buttons 1 and 2 |
| 2 | 2 (EXP1_12) | 3.3 V | Common for buttons 3 and 4 |
| 3 | 7 | BTN1 | Button 1 signal |
| 4 | 9 | BTN2 | Button 2 signal |
| 5 | 13 | BTN3 | Button 3 signal |
| 6 | 15 | BTN4 | Button 4 signal |

### 3. Home button

The Home button is located at the rear of the printer body.

| Connection | EXP1 pin |
|---|---|
| Home button connection 1 | EXP1_1 |
| Home button connection 2 | EXP1_3 |

### 4. Extruder mode switch

The extruder mode switch controls the feed, retract, and print functions.

Pins are numbered from top to bottom, viewed using the connector orientation described above.

| Physical pin | EXP1 pin |
|---:|---:|
| 1 | 7 |
| 2 | 8 |
| 3 | 5 |
| 4 | 6 |

## Firmware

The firmware image is named:

```text
mksLite.bin
```

This is intended for the EasyThreeD K9 equipped with the ET4000+ board. Do not assume it is compatible with other K9 board revisions or other EasyThreeD printer models.

## Contributing and reporting problems

Testing and feedback are welcome.

When reporting an issue, include:

- Printer model and control-board revision.
- Firmware version or Git commit.
- Description of the problem.
- Steps required to reproduce it.
- Relevant photographs, logs, or serial output.

Hardware observations, corrections to pin mappings, and firmware improvements are especially welcome.

## Credits and references

This project builds on the wider EasyThreeD STM32 Marlin firmware development work.

- [schmttc/EasyThreeD-K7-STM32](https://github.com/schmttc/EasyThreeD-K7-STM32)
- [Original K9 hardware discussion — Issue #10](https://github.com/schmttc/EasyThreeD-K7-STM32/issues/10)

Please retain appropriate upstream attribution and licensing notices when modifying or redistributing the firmware.

---

**Project scope:** EasyThreeD K9 · ET4000+ control board · Marlin 2
