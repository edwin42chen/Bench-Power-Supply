# Bench Power Supply

## Overview
A mains-powered, adjustable bench power supply designed in KiCad, converting 120V AC wall input into a regulated 1–20V DC output through a custom signal chain.

## Objectives
- Design a mains-powered adjustable DC power supply from raw 120V AC input
- Provide adjustable output voltage across a wide range
- Display live output voltage and current readings during use
- Diagnose and resolve hardware faults through systematic circuit-level debugging

## Key Components
- **AC Input Stage** — fuse, step-down transformer, bridge rectifier
- **Buck Converter** — XL4016, regulating output across the 1–20V DC range
- **Current Sensing** — INA219 current-sensing IC
- **Display/Control** — Arduino Nano driving an LCD screen, powered directly from the board's onboard 5V regulator, showing live voltage/current readings

## Signal Chain
AC Input → Fuse → Transformer → Bridge Rectifier → XL4016 Buck Converter → Regulated 1–20V DC Output

## Design Notes
- **Voltage Regulation**: The XL4016 buck converter regulates the output across a 1–20V DC range.
- **Monitoring**: An INA219 current-sensing IC feeds voltage and current data to an Arduino Nano, which drives an LCD display for real-time monitoring during use.
- **Debugging**: When the board experienced a fuse-blowing fault, I diagnosed it through stage-by-stage isolation testing, cross-referencing component datasheets with multimeter measurements to systematically test and rule out each stage of the circuit (transformer wiring, rectifier diodes, filter capacitors).
