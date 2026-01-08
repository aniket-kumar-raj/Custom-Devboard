# Custom-Devboard
Story of Creation of My first Devboard


# My RP2040 Devboard Journal
**Author:** [Your Name]
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
