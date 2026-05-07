# Mini-PC-for-Embedded-Linux

# Schematic Design of an Allwinner H3 Based Mini PC for Embedded Linux Applications

## Project Overview

This project presents the schematic-level design of a compact Mini PC system based on the Allwinner H3 application processor. The system is designed to support Embedded Linux booting using external DDR3 memory and non-volatile boot storage such as SPI Flash and Micro SD card.

The design includes major hardware blocks required for a Linux-capable embedded computer, including processor, DDR3 RAM, SPI Flash, Micro SD card, USB interfaces, HDMI display output, Wi-Fi/Bluetooth connectivity, reset circuitry, clock generation, and power management.

## Main Features

- Allwinner H3 application processor
- 1 GB DDR3 RAM using two 512 MB DDR3 devices
- SPI Flash boot support
- Micro SD card boot support
- USB-C OTG interface
- USB host interface
- HDMI display output
- RTL8723DS Wi-Fi/Bluetooth module
- Multi-rail power management
- Schematic-only implementation

## DDR3 Memory Architecture

The design uses two AS4C256M16D3L DDR3 devices. Each device has 512 MB capacity and 16-bit data width.

DDR1 handles DQ[0..15], while DDR2 handles DQ[16..31]. Both DDR devices share the same address and control buses. Together, they form a 32-bit DDR interface with total memory capacity of 1 GB.

## Booting Process

The booting sequence is:

1. Power rails stabilize.
2. Reset is released.
3. Internal Boot ROM starts execution.
4. Boot device is detected.
5. SPL is loaded into internal SRAM.
6. DDR3 memory is initialized.
7. U-Boot is loaded into DDR3.
8. Linux kernel and device tree are loaded.
9. Linux starts executing from DDR3 RAM.

## Dumping / Programming Process

The Linux image can be written to a Micro SD card using tools such as Balena Etcher, Win32 Disk Imager, or the Linux `dd` command.

SPI Flash can be programmed using USB FEL mode or an external SPI programmer.

## Reason for Schematic-Only Design

PCB layout is not implemented because the Allwinner H3 is a BGA package device. A practical PCB layout requires multilayer routing, BGA fanout, DDR3 length matching, controlled impedance routing for USB and HDMI, power integrity analysis, and signal integrity verification.

## Repository Contents

| Folder | Description |
|---|---|
| Report | IEEE LaTeX report and final PDF |
| Schematic | KiCad schematic files and schematic PDF |
| Figures | Images used in the report |
| Documents | Datasheets and reference documents |

## Tools Used

- KiCad
- LaTeX / Overleaf
- GitHub
- Embedded Linux references
- Allwinner H3 documentation

## Author

Gudisa Dinesh Reddy  
MT2025509  
International Institute of Information Technology Bangalore
