# Lesson 08 — Devicetree

> Spine: [Devicetree](https://docs.zephyrproject.org/latest/build/dts/index.html) · [HOWTOs](https://docs.zephyrproject.org/latest/build/dts/howtos.html)
> Concept: hardware is data. Overlays change that data without `#ifdef BOARD` soup.
> Run: `native_sim` build + a test or `west build -t ram_report`/`-t dt_minimal` evidence you can explain. Prefer a ztest that reads a `DT_NODELABEL` / chosen node.

## Read first

- [ ] Nodes, properties, labels, aliases, chosen
- [ ] Application overlay (`app.overlay`)
- [ ] `DT_NODELABEL`, `GPIO_DT_SPEC_GET` (you may only *print* or assert a node exists on native_sim)

## Plan of work

- **A. Read first**
- **B.** `app.overlay` that adds or changes a node `native_sim` will still build with
- **C.** C that uses a DT macro. Test or log the value you overlaid
- **D.** `NOTES.md`: generated `zephyr.dts` snippet (path under `build/`) and what your overlay changed
- **E.** `@checkpoint`

## Definition of done

You can point at overlay → generated DTS → C macro without saying "the board files magically know."
