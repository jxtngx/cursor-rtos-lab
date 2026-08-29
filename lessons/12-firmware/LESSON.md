# Lesson 12 — Firmware you can explain

> Spine: lessons 02–11 · kernel services index
> Destination: one concurrent app on **simulators**. Not a product. Not a vendor demo.

## Contract

The tutor may map threads.
The tutor may not paste philosophers + a driver + a shell as "your" firmware.

## Read first

- [ ] Your NOTES from 02, 04, 05, 11

## Plan of work

- **A. Read first**
- **B.** Diagram in `NOTES.md`: threads, a sync object, a timer or work item, one DT/driver use from 08/10
- **C.** Wire *your* code. ztest the invariants (counts, "work ran once", no sleep in ISR)
- **D.** `west twister -p native_sim -p qemu_cortex_m3`
- **E.** `@checkpoint`

## Definition of done

You can redraw the firmware: who runs, who waits, what the timer defers, which node the driver binds.
A stranger can twister it with no board.

## What this lesson is not

- Bluetooth, networking, or a bootloader
- `west flash` as a trophy
- A factory dump of a full product firmware
