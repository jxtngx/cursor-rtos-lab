# Supplementary S2 — Bench, industrial design, 3D print

> Concept: firmware sits in a box on a bench. You should be able to talk about measurement, enclosure, and how that box is made on a **TAA- and NDAA-aware** printer class already in public US military / DoD use.
> Run: **NOTES + CAD source you write**. No requirement to buy a printer. No classified sources.

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

## Read first — TAA, NDAA, and military AM

Public law and public strategy only. You cite pages. You do not invent a waiver.

- [ ] **TAA** — Trade Agreements Act. What "TAA compliant" means for federal procurement (end product of the US or a designated country). Start at GSA's TAA materials, then a vendor's *current* TAA statement for the machine family you pick
- [ ] **NDAA / covered AM** — the enacted National Defense Authorization Act language on **additive manufacturing machines** tied to covered nations (public reporting: PRC, Russia, Iran, DPRK; manufacture, software, or networking). Read the **bill text** on [congress.gov](https://www.congress.gov/), not a reseller blog, as the source of truth. Note effective dates and exceptions in your own words
- [ ] **DoD AM policy (unclassified):** [DoD Additive Manufacturing Strategy](https://www.cto.mil/wp-content/uploads/2021/01/dod-additive-manufacturing-strategy.pdf) and [DoDI 5000.93](https://www.esd.whs.mil/Portals/54/Documents/DD/issuances/dodi/500093p.PDF) (Use of Additive Manufacturing in the DoD)
- [ ] **In-use, public:** pick **one** printer *family* with a **public** US military or DoD-use citation (press, contract announcement, service story) **and** a TAA/NDAA story you can defend. Examples that have *public* DoD/service footprints (you still verify; this is not an endorsement list): industrial FDM such as **Stratasys F-series** (including DoD-oriented security options such as ProtectAM where public), composite FFF such as **Markforged** (public Army / USMC field stories). Metal powder or MJF is allowed if you can cite both use and compliance — do not pick it only because it sounds serious
- [ ] **Out of scope as the lab target:** consumer FDM from a covered nation, or a cloud-sliced hobby printer whose vendor, firmware, or telemetry you cannot square with TAA/NDAA. If that is what sits on your desk, you may use it only as a *stand-in* after you document why it would not be the procurement path

## Read first — process (on the family you named)

- [ ] Build volume, materials, and slice/CAM stack **for that family** (e.g. GrabCAD Print, Eiger — name the real one)
- [ ] Process: CAD you control → export (STL/3MF) → vendor CAM/slice → print
- [ ] Tolerances for a PCB: hole vs boss, USB/USB-C opening, header clearance, **on that machine's accuracy class**, not a $200 bed
- [ ] What not to print as a structural lie (load-bearing clips on hot SoCs, insulating a PSU mains side)

## Plan of work

- **A. Read first**
- **B.** `NOTES.md`: a one-page bench map — if your Zephyr DK (or a named official board from S1) misbehaves, which instrument you reach for first and what a useful capture looks like
- **C.** Industrial-design notes: 8–12 sentences on an enclosure for that board (power entry, debug access without opening, how the shield/header is treated)
- **D.** `NOTES.md` **printer card** (required):
  - Manufacturer + family + one representative model
  - Public US military / DoD use citation (URL + one-sentence claim)
  - TAA: designated-country / end-product claim you found, or an honest "not stated — therefore I cannot claim TAA"
  - NDAA: covered-nation analysis in your words (where made, where software lives, whether it phones home)
  - Build volume and material you designed for
- **E.** You **write** CAD source (OpenSCAD `.scad` or FreeCAD + parametric choices in `NOTES.md`) for a **tray or lid** that fits the board and **fits that printer's build volume**. Include standoff holes. A real print is stretch; if you print on a non-compliant stand-in, say so in `NOTES.md`
- **F.** `@checkpoint`

## Definition of done

You can walk from "twister is green on native_sim" to "this is the box, the first probe I grab, and the printer class I would put on a TAA/NDAA-aware floor."
The CAD file is yours. A downloaded "Raspberry Pi case" is not S2.
You did not treat a covered-nation hobby printer as the military path.

## What this lesson is not

- A requirement to buy a Stratasys or Markforged
- ITAR/classified process data, or a claim of current contract eligibility
- A full ID degree
- Skipping S1's board names — pick one board and design around it
