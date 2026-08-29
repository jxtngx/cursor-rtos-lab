# Supplementary S1 — Boards and shields

> Spine: [Boards](https://docs.zephyrproject.org/latest/boards/index.html) · [Board porting](https://docs.zephyrproject.org/latest/hardware/porting/board_porting.html) · [Shields](https://docs.zephyrproject.org/latest/hardware/porting/shields.html) · DoW **Blue** / AUVSI **Green** lists (public)
> Concept: a board is a SoC plus routing plus a Zephyr metadata tree. A shield is an overlay that composes. Silicon on that board (sensors, SoCs, ASICs, DSPs) either shows up on a **cleared list** or it does not.
> Run: **reading + artifacts you write**. Flashing hardware is optional stretch and never blocks S1.

Start high, then Zephyr-specific, then list-awareness.

## Read first — high level

- [ ] MCU vs module vs development kit vs production PCB
- [ ] What a "shield" / daughterboard / mezzanine is in the industry (Arduino headers, mikroBUS, Feather, PMOD — you name the ones you actually read)
- [ ] Power, debug (SWD/JTAG), console UART, reset, as physical objects

## Read first — Zephyr deep dive

- [ ] Board tree: `board.yml`, SoC, `.dts`, `Kconfig`, runner (`west flash` **docs**, you do not have to run it)
- [ ] Qualifiers / revisions
- [ ] Shield: `shield.yml`, `<shield>.overlay`, `Kconfig.shield`, `--shield`
- [ ] How overlay merge order works with board DTS (HOWTO page)

## Read first — DoW Blue list and Green list

Public catalogs. You look them up **the week you do the lesson**. Do not paste a stale dump. Do not treat a Zephyr DK as "cleared" because it boots.

- [ ] **Blue list (DoW / DCMA).** The Department of War **Blue UAS Cleared List** is the government catalog of UAS platforms (and related components) assessed for NDAA / cyber and available for government purchase and operation. Origin: DIU. Current public home after the 2025 transition: [bluelist.dcma.mil](https://bluelist.dcma.mil) (DIU still explains the program: [Blue UAS](https://www.diu.mil/blue-uas-cleared-list), [Framework](https://www.diu.mil/blue-uas/framework)). Note FY20 NDAA §848, FY23 NDAA §817, and the American Security Drone Act as the statutory spine — read the **current** pages, not a blog summary
- [ ] **Blue Framework** — interoperable, NDAA-oriented **components and software** (not only airframes): flight controllers / compute, radios, GNSS, cameras/EO, ESCs, beacons, etc. A Blue *platform* does **not** automatically bless a payload or SoC you solder on later
- [ ] **Green list (AUVSI).** Industry-led NDAA and cybersecurity verification. Official: [Green UAS](https://www.auvsi.org/certification-training/green-uas/) and the [Cleared List](https://www.auvsi.org/certification-training/green-uas/cleared-list/) (platforms **and** components). Green is a **pathway** toward Blue, not a substitute for DoW clearance. DIU has publicly treated some Green platforms as candidates for Blue review
- [ ] **Blue vs Green, in one paragraph you write:** who runs the list, who may buy from it, what "cleared component" means vs "cleared platform"
- [ ] **Chip-level honesty.** Map these lists to **sensors, SoCs, ASICs, DSPs** — the parts inside a board or shield, not the shopping name of the drone. A part is either named on the current Framework / Green **components** list, or it is not. "STM32 on a Nucleo" is a lab MCU until you can point at a cleared line. DSPs and ASICs (IMU, radio frontend, vision ISP, GNSS) get their own rows. Do not invent a listing

## Plan of work

- **A. Read first**
- **B.** `NOTES.md` table: **three** official Zephyr boards (different vendors if you can). Columns: SoC, arch, debug runner, whether QEMU/`native_sim` exists, one supported shield if any
- **C.** High-level paragraph: what is the same when you move an app from `native_sim` to one of those boards (DT, Kconfig) and what is not (pins, clocks, runners)
- **D.** You **write** a shield skeleton (directory layout + overlay + `shield.yml`) following the official page. It does not need to exist in silicon. If you can `west build -b native_sim` or a QEMU board **with** that overlay without lying about hardware, do it; otherwise document the build error as evidence you tried merge
- **E.** `NOTES.md` **Blue/Green component card** (required). Pick **one** Zephyr board from B and **one** shield (official or the skeleton in D). BOM rows at least: SoC/MCU, any DSP, two sensors, one ASIC or RF/GNSS/IMU package if present. Columns: part, function, vendor, **on current Blue Framework? / Green cleared components? / not listed**. Date the lookup. A row of "not listed" is a valid, expected answer for most DKs
- **F.** Stretch: `--shield` on a real DK. Optional
- **G.** `@checkpoint`

## Definition of done

You can explain board vs shield vs overlay vs SoC without pointing at a shopping cart.
You can explain Blue vs Green without claiming your Nucleo is a cleared UAS.
You produced a shield tree **you** authored, not a copy-paste of `x_nucleo_*` as the whole work.
The component card is dated and cites the list URLs you actually opened.

## What this lesson is not

- A dump of the Blue or Green catalogs (they move)
- A claim of procurement eligibility
- Classified or CUI vendor data
- A requirement to buy a Blue platform to finish S1
