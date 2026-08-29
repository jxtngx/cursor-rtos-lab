# Lesson 05 — Timers and workqueues

> Spine: [Timers](https://docs.zephyrproject.org/latest/kernel/services/timing/timers.html) · [Workqueue threads](https://docs.zephyrproject.org/latest/kernel/services/threads/workqueue.html)
> Concept: a timer callback is not a thread. Deferred work exists so you do not do heavy work in the wrong context.
> Run: ztest on `native_sim`

## Read first

- [ ] `k_timer` start, status, period vs one-shot
- [ ] System workqueue vs a queue you create
- [ ] What is legal in a timer expiry function

## Plan of work

- **A. Read first**
- **B.** One-shot timer that submits work. Test that work ran (counter / flag)
- **C.** `NOTES.md`: ISR/timer context vs thread context in your app
- **D.** `@checkpoint`

## Definition of done

You can say why `k_malloc` in a timer expiry may be the wrong idea (even if a given config allows it).
