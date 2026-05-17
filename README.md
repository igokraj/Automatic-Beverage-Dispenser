# Automatic Beverage Dispenser

# 3D view of the board
```bash
Images
```
Hardware design of a control unit for an automatic beverage dispenser. The system manages liquid pump operations based on readings from a hardware flow sensor. 

## Hardware Specifications
* **Microcontroller:** 32-bit STM32G030F6P6 in a TSSOP20 package.
* **Power Supply:** 12V DC via a barrel jack connector. The power path is protected by a 1812L150/24 resettable fuse against short circuits, an SMBJ15A TVS diode against overvoltage spikes, and a B340 Schottky diode against reverse polarity. The digital logic is powered by an AMS1117-3.3 LDO regulator.
* **Power Stage:** An AO3400 N-Channel MOSFET operating as a low-side switch to control the liquid pump. The inductive load is protected by an SS14 flyback diode.
* **Input Interfaces:** Three user buttons (UP, DOWN, START) equipped with hardware RC debouncing circuits. The flow sensor input utilizes a resistor voltage divider (27k/10k) to safely step down the 12V signal to a 3.3V logic level.
* **External Communication:** An I2C bus with hardware 4.7k pull-up resistors to 3.3V, alongside a standard SWD header for microcontroller programming and debugging.
* **PCB:** Two-layer FR-4 board utilizing copper pours to minimize electromagnetic interference (EMI).

## Repository Structure
* `/Production` - A complete set of manufacturing files optimized for PCBA assembly (Gerber files, Excellon drill files, CSV BOM, and Pick & Place CPL file).
* Files in the root directory represent the printed circuit board project sources, designed in KiCad.

## Installation
Clone this repository to your local machine:
```bash
git clone https://github.com/igokraj/Automatic-Beverage-Dispenser.git
cd Automatic-Beverage-Dispenser
