# Supplementary S1 — Boards and shields

> Spine: [Boards](https://docs.zephyrproject.org/latest/boards/index.html) · [Board porting](https://docs.zephyrproject.org/latest/hardware/porting/board_porting.html) · [Shields](https://docs.zephyrproject.org/latest/hardware/porting/shields.html)
> Concept: a board is a SoC plus routing plus a Zephyr metadata tree. A shield is an overlay that composes.
> Run: **reading + artifacts you write**. Flashing hardware is optional stretch and never blocks S1.

Start high, then Zephyr-specific.

## Read first — high level

- [ ] MCU vs module vs development kit vs production PCB
- [ ] What a "shield" / daughterboard / mezzanine is in the industry (Arduino headers, mikroBUS, Feather, PMOD — you name the ones you actually read)
- [ ] Power, debug (SWD/JTAG), console UART, reset, as physical objects

## Read first — Zephyr deep dive

- [ ] Board tree: `board.yml`, SoC, `.dts`, `Kconfig`, runner (`west flash` **docs**, you do not have to run it)
- [ ] Qualifiers / revisions
- [ ] Shield: `shield.yml`, `<shield>.overlay`, `Kconfig.shield`, `--shield`
- [ ] How overlay merge order works with board DTS (HOWTO page)

## Plan of work

- **A. Read first**
- **B.** `NOTES.md` table: **three** official Zephyr boards (different vendors if you can). Columns: SoC, arch, debug runner, whether QEMU/`native_sim` exists, one supported shield if any
- **C.** High-level paragraph: what is the same when you move an app from `native_sim` to one of those boards (DT, Kconfig) and what is not (pins, clocks, runners)
- **D.** You **write** a shield skeleton (directory layout + overlay + `shield.yml`) following the official page. It does not need to exist in silicon. If you can `west build -b native_sim` or a QEMU board **with** that overlay without lying about hardware, do it; otherwise document the build error as evidence you tried merge
- **E.** Stretch: `--shield` on a real DK. Optional
- **F.** `@checkpoint`

## Definition of done

You can explain board vs shield vs overlay vs SoC without pointing at a shopping cart.
You produced a shield tree **you** authored, not a copy-paste of `x_nucleo_*` as the whole work.
