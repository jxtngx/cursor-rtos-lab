# Lesson 04 — Synchronization

> Spine: [Semaphores](https://docs.zephyrproject.org/latest/kernel/services/synchronization/semaphores.html) · [Mutexes](https://docs.zephyrproject.org/latest/kernel/services/synchronization/mutexes.html) · [Polling](https://docs.zephyrproject.org/latest/kernel/services/polling.html)
> Concept: a race is a spec bug. Sem, mutex, and poll are different tools.
> Run: ztest on `native_sim`

## Read first

- [ ] `k_sem` give/take, initial count
- [ ] `k_mutex` recursive or not — read the page
- [ ] `k_poll` when you wait on more than one thing

## Plan of work

- **A. Read first**
- **B.** Producer/consumer with a semaphore. Test the final count
- **C.** Shared data with a mutex. Test that a torn write cannot appear (small critical section you can reason about)
- **D.** One `k_poll` wait (sem or signal). Test it wakes
- **E.** `@checkpoint`

## Definition of done

You can name which primitive you would **not** use for mutual exclusion and why.
