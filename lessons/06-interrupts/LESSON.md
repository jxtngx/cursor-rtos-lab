# Lesson 06 — Interrupts

> Spine: [Interrupts](https://docs.zephyrproject.org/latest/kernel/services/interrupts.html)
> Concept: an ISR is a different C world: no sleeping, short work, then a thread.
> Run: ztest on `native_sim`. Also build on `qemu_cortex_m3`.

## Read first

- [ ] IRQ_CONNECT / `irq_enable`
- [ ] What ISRs may call (and must not)
- [ ] `irq_offload` or a software-triggered IRQ on `native_sim` so you do not need a pin

## Plan of work

- **A. Read first**
- **B.** ISR (or offload) that gives a sem. Test thread takes the sem
- **C.** `NOTES.md`: list three APIs you must not call from the ISR
- **D.** Build on `qemu_cortex_m3` even if the offload path is native_sim-specific — split with `#ifdef` or a second testcase.yaml filter you can explain
- **E.** `@checkpoint`

## Definition of done

You can explain how a flag from an ISR becomes thread work without spinning in the ISR.
