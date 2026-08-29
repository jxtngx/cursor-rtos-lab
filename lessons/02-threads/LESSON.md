# Lesson 02 — Threads

> Spine: [Threads](https://docs.zephyrproject.org/latest/kernel/services/threads/index.html)
> Concept: a thread has a stack, a priority, and an entry. `main` is not the only context.
> Run: ztest on `native_sim`

## Read first

- [ ] `K_THREAD_DEFINE` vs `k_thread_create`
- [ ] Stack size, entry, `k_tid_t`
- [ ] Sleep vs busy loop

## Plan of work

- **A. Read first**
- **B.** Failing ztest: a worker thread does not yet increment a counter the test waits on
- **C.** Spawn a thread, sleep in the test thread, assert the count
- **D.** `NOTES.md`: who owns the stack buffer
- **E.** `@checkpoint`

## You write

Out-of-tree app + ztest. No paste of `samples/philosophers`.

## Definition of done

You can draw two threads and the counter without looking at the code.
