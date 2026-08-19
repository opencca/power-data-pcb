# PCB to Split USB-C Power and Data

The Rock 5B RK3588 multiplexes a single USB-C PD port for both power and USB data.
For frequent firmware flashing, connecting this port directly to a host is convenient because it
directly provides access to MaskROM mode to flash opencca firmware.

<img width="500" alt="image" src="./pcb-rk3588.jpg" />


Many hosts cannot supply enough current for the board to operate reliably under high load.

This repository provides a custom PCB that de-multiplexes the USB-C PD connection back into
- USB 2.0 data line for flashing
- and a dedicated power input for external power supply.

### Design files
`src` contains a KiCad project with the board's schematic and a PCB layout.

`src/gen` contains pre-generated Gerber and Drill files for printing.

### Part list
Each board requires these parts:
- 3x GCT USB4105-GF-A: USB-C receptacle, USB 2.0 (16-pin), top-mount horizontal, TH shield legs (Footprint: `Connector_USB:USB_C_Receptacle_GCT_USB4105-xx-A_16P_TopMnt_Horizontal`)
- 2x 5.1kΩ resistor, 0805 (2012 metric), ±1% (Footprint: `Resistor_SMD:R_0805_2012Metric_Pad1.20x1.40mm_HandSolder`)

Optionally the board contains 3 mounting holes for 3.2mm M3 screws.

### Credits 
The circuit topology of this board is based on a schematic provided by [CentyLab](https://www.elecrow.com/usb-c-splitter-androidauto-carplay.html) ([web archive](https://web.archive.org/web/20260819090238/https://www.elecrow.com/usb-c-splitter-androidauto-carplay.html)).
It was used as a functional reference only, all schematic and PCB files were drawn independently in KiCad.
