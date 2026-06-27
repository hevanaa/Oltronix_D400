# Oltronix D400-007D Regulator Board (KiCad redesign)

This repository contains a redesigned regulator board for the Oltronix D400-007D 400 V DC power supply.

The goal of this redesign is improved safety margins, better component availability, and improved PCB high-voltage layout compared to the original design.

---

## Project structure

- `/project/`  
  KiCad PCB and schematic files

- `/production/`  
  Gerber files, drill files

- `/docs/`  
  Documentation, and reference material

- `/bom/`  
  Bill of Materials (CSV / spreadsheet format)

---

## Design overview

This board replaces the original regulator / error amplifier section of the power supply.

Key improvements include:
- Increased high-voltage clearance in critical areas
- Improved creepage distance at edge connector
- Use of modern, readily available components
- Slight circuit refinements for reliability (e.g. protection diode on driver stage)

---

## PCB design notes

### Edge connector safety improvement

The original design used a single-sided PCB edge connector layout, resulting in insufficient clearance between high-voltage pins (notably 220 V AC input and ~320–360 V DC rail).

This redesign uses a **double-sided alternating pad layout**, where connector contacts are split between top and bottom layers.

This achieves:
- Significantly increased creepage distance (>5 mm effective)
- Reduced risk of carbon tracking and flashover
- Improved robustness under contamination and aging

Pad geometry was also adjusted to better match connector cavity dimensions.

---

## Component labeling convention

This project follows the original Oltronix reference designators where possible.

- **T1, T2, T3** → Transistors  
- **D1, D2, D3** → Diodes  
- **Rxx** → Resistors (high-voltage / power-rated where specified)  
- **Cxx** → Capacitors  
- **P1** → Adjustment potentiometer / calibration trimmer  

When deviations from the original design exist, they are documented in the schematic notes.

---

## Manufacturing notes

- Standard 1.6 mm FR-4 PCB thickness assumed
- High-voltage areas require clean routing and no solder mask contamination in critical creepage zones
- Some resistors must withstand elevated voltage stress and should not be substituted with generic low-voltage types

---

## Adjustments

P1 must be adjusted during commissioning as described in the accompanying blog article:
https://baldpenguin.blogspot.com/2026/04/another-oltronix-power-supply-d400-007d.html

---

## License

This project is licensed under the CERN-OHL-S v2 (Strongly Reciprocal).

See `LICENSE` file for details.
