# Lesson 07 — Memory

> Spine: [Memory management](https://docs.zephyrproject.org/latest/kernel/memory_management/index.html) · thread stacks from lesson 02
> Concept: embedded heaps are optional and finite. Stack overflow is a real bug, not a theory.
> Run: ztest on `native_sim`

## Read first

- [ ] Thread stack vs kernel heap vs memory slabs / blocks
- [ ] `k_malloc` / `k_free` and when to prefer a slab
- [ ] Stack canaries / sentinel (read what your `prj.conf` actually enables)

## Plan of work

- **A. Read first**
- **B.** Allocate from heap, free, allocate again. Test
- **C.** Memory slab of fixed blocks. Test exhaustion returns the documented error
- **D.** `NOTES.md`: stack size you chose for a worker and how you would notice overflow on sim
- **E.** `@checkpoint`

## Definition of done

You can say why `malloc` from newlib (if enabled) is not the same object as `k_malloc`.
