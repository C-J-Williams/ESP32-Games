# PCB Design & Manufacturing Files

This folder contains the design and manufacturing files for the ESP32 Games Machine custom printed circuit board (PCB).

The files include the component Bill of Materials (BOM), Gerber manufacturing files and the original PCB design file.

## Included Files

### 1. Bill of Materials (BOM)
**File:** `BOM_Games_Machine_2026-11-23.csv`

The Bill of Materials (BOM) contains a list of the electronic components required to assemble the PCB.

It includes information such as:
- Component descriptions and names.
- PCB reference designators.
- Component footprints.
- Required quantities.
- Manufacturer and supplier details.
- Supplier part numbers and pricing information, where available.

The BOM can be opened using Microsoft Excel, LibreOffice Calc or another spreadsheet application.

It can also be used to help source and purchase the components needed to assemble the board. The BOM can be uploaded to LCSC.com and all parts can be purchased and shipped directly for self assembly.

### 2. Gerber Manufacturing Files
**File:** `Gerber_Games_Machine_v2-003_2026-11-23.zip`

This ZIP archive contains the Gerber files required to manufacture the printed circuit board.

Gerber files describe the physical PCB layout, including:
- Copper layer patterns.
- Solder mask layers.
- Silkscreen markings.
- Board outline and dimensions.
- Drill locations and hole information.

These files can be supplied directly to a PCB manufacturer when ordering the circuit board.

**This is the file required if you simply want to have the PCB manufactured.**

The Gerber and the BOM can be uploaded to JLCPCB.com and they manufacture the board and can solder the components for you as well. The prices are reasonable and the delivery is fast.

### 3. Original PCB Design File
**File:** `PCB_v2-003_2026-11-23.json`

This is the original PCB design file exported in JSON format.

It contains the underlying PCB design information, including component placement, footprints, board layout and electrical connections.

The file is provided for anyone wishing to inspect, modify or further develop the PCB design.

It can be imported into a compatible PCB design application, such as EasyEDA, to continue working on the design.

## PCB Version Information

The files in this folder relate to:

- **Project:** ESP32 Games Machine
- **PCB Version:** v0.10.26.3
- **Date:** 23 November 2026

The version number and date are included in the filenames to help identify the correct design and ensure that the manufacturing files, component list and PCB design correspond to the same revision.

---

All files are provided as part of the ESP32 Games Machine project.
