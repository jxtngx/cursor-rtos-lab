# Supplementary S2 — Bench, industrial design, 3D print

> Concept: firmware sits in a box on a bench. You should be able to talk about measurement, enclosure, and how a hobbyist FDM part becomes that box.
> Run: **NOTES + CAD source you write**. No store run required. No "buy this exact oscilloscope" mandate.

The prompt for this lesson stopped at "3D printing with". This lab treats that as **hobbyist FDM**: CAD you control → slicer → printer. Default CAD: **FreeCAD** and/or **OpenSCAD** (you pick one and stay with it). Default slicer family: PrusaSlicer / OrcaSlicer or the slicer that actually drives your printer. Name what you used.

## Read first — hobbyist bench (EE)

- [ ] Safety: ESD, mains vs extra-low voltage, current-limited PSU
- [ ] Tools you can describe without owning all of them: DMM, adjustable PSU, soldering iron, hot-air, logic analyzer, entry oscilloscope, crimp tools
- [ ] What each tool **answers** (voltage present, edge timing, protocol decode, thermal joint)
- [ ] Debug: 3v3 vs 5V, common ground, SWD/JTAG header vs USB-serial

## Read first — industrial design (concepts)

- [ ] Enclosure jobs: strain relief, connector access, button/LED features, thermal path, service vs sealed
- [ ] DFM for a two-piece shell: bosses, standoffs, draft, snap vs screw, PCB keep-out
- [ ] Labeling, revision of a mechanical part vs firmware revision
- [ ] IP / drop / heat as **questions**, not a certification you fake

## Read first — 3D printing (hobbyist FDM)

- [ ] Process: model → STL/3MF → slice (layer height, infill, supports, walls) → print
- [ ] Tolerances for a PCB: hole vs boss, USB/USB-C opening, header clearance
- [ ] Material: PLA vs PETG vs ABS as a **use** choice (heat, toughness), not a brand loyalty test
- [ ] What not to print as a structural lie (load-bearing clips on hot SoCs, insulating a PSU mains side)

## Plan of work

- **A. Read first**
- **B.** `NOTES.md`: a one-page bench map — if your Zephyr DK (or a named official board from S1) misbehaves, which instrument you reach for first and what a useful capture looks like
- **C.** Industrial-design notes: 8–12 sentences on an enclosure for that board (power entry, debug access without opening, how the shield/header is treated)
- **D.** You **write** CAD source (OpenSCAD `.scad` or FreeCAD-exported model + the parametric choices in `NOTES.md`) for a **tray or lid** that matches the board outline from the vendor drawing or a measured rectangle you recorded. Include standoff holes. This is the 3D-print artifact. Slicing a real print is stretch
- **E.** `@checkpoint`

## Definition of done

You can walk from "twister is green on native_sim" to "this is the box and the first probe I grab" without a shopping-list essay.
The CAD file is yours. A downloaded "Raspberry Pi case" is not S2.

## What this lesson is not

- A requirement to buy a Keysight bench
- A full ID degree
- CNC/metal as a gate (FDM is enough)
- Skipping S1's board names — pick one board and design around it
