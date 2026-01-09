# Custom-Devboard
Story of Creation of My first Devboard


# My RP2040 Devboard Journal
**Author:** Aniket Kumar Raj
**Project:** Custom RP2040 Development Board
**System:** Windows 7 (32-bit)

---

## Log: Jan 8, 2026 - Setting up the Environment

### What I did today:
* **Research:** Read through the [Hack Club Blueprint Devboard guide](https://blueprint.hackclub.com/starter-projects/devboard).
* **Environment Setup:** Realized my computer is running **Windows 7 32-bit**, which doesn't support the latest KiCad 8.0.
* **Problem Solving:** Found an archive of **KiCad 5.1.12 (i686)** which is compatible with 32-bit systems. 
* **Download:** Started downloading the full installer to ensure I have all the symbols and footprints for the RP2040.

### Challenges:
* Modern documentation for the RP2040 usually assumes you are using KiCad 7 or 8. I will have to adapt the steps (like finding the "Add Text" tool) to the older KiCad 5 interface.
* Ensuring the 32-bit version has the specific **RP2040 library**, as this chip was released after KiCad 5 was first made. I might need to import the library manually.

### Next Steps:
* Finish the installation of KiCad 5.1.12.
* Start a new project and begin the **Schematic** (Eeschema).
* Map out the power circuit (5V to 3.3V) and the USB-C data lines.
* **Goal:** Get my name on the Silkscreen layer of the PCB layout!

---

## Hardware Specifications
* **MCU:** RP2040
* **Storage:** 16MB Flash (W25Q128)
* **Connectivity:** USB-C
* **Custom Feature:** Custom Silkscreen branding and a unique PCB shape.



# Engineering Journal: RP2040 PCB Project

## [2026-01-09] - BOM Optimization & Component Validation

### Summary
Today’s focus was on a deep-clean of the Bill of Materials (BOM) for the RP2040 custom board. Major discrepancies were identified between the intended electrical values and the selected LCSC part numbers. All critical resistors, capacitors, and the flash memory chip were cross-verified against the JLCPCB assembly library to ensure first-time-right manufacturing.

### Technical Tasks & Updates
- **USB Data Line Calibration:**
  - Corrected R1 and R2 to **27Ω** (LCSC: **C17594**). 
  - *Previous error:* Found a 10kΩ/100Ω mismatch in the part numbers which would have caused USB communication failure.
- **USB-C Power Negotiation:**
  - Validated R3 and R4 as **5.1kΩ** (LCSC: **C26023**).
  - Ensured the footprint is **0805** to match the PCB pads (previously incorrectly set to 0402).
- **Flash Memory Selection:**
  - Finalized U3 (NOR Flash) as **W25Q128JVSIQ** (LCSC: **C97521**).
  - Confirmed 128Mb (16MB) capacity and SOIC-8-208mil package compatibility.
- **Status Indicator:**
  - Corrected R8 for the LED to **330Ω** (LCSC: **C17630**) to ensure visible brightness.

### BOM Checklist (Verified 0805 Parts)
| Designator | Value | LCSC Part # | Role |
| :--- | :--- | :--- | :--- |
| R1, R2 | 27Ω | C17594 | USB Differential Pair Termination |
| R3, R4 | 5.1kΩ | C26023 | USB-C Configuration Channel (CC) |
| R5, R7 | 10kΩ | C17414 | Pull-up Resistors |
| R6 | 1kΩ | C17513 | Signal Limiting |
| R8 | 330Ω | C17630 | LED Current Limiting |
| U3 | 16MB Flash | C97521 | Program Storage (Basic Part) |

### Next Steps
- [ ] Export the final BOM as a Comma-Separated CSV.
- [ ] Perform a 3D Preview check on JLCPCB for the **U1 (RP2040)** and **U3 (Flash)** orientation (Pin 1 alignment).
- [ ] Verify the **J1 (USB-C)** edge clearance to ensure cables can fully seat in the connector.
- [ ] Finalize the order for assembly.

---

