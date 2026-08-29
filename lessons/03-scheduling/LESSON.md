# Lesson 03 — Scheduling

> Spine: [Scheduling](https://docs.zephyrproject.org/latest/kernel/services/scheduling/index.html)
> Concept: priorities and time-slicing are policy. Cooperative vs preemptive is not a slogan.
> Run: ztest on `native_sim`

## Read first

- [ ] Preemptive vs cooperative
- [ ] Priority numbers in Zephyr (lower number = higher priority)
- [ ] Time slicing Kconfig

## Plan of work

- **A. Read first**
- **B.** Two threads, same vs different priority. Record who runs. Test the outcome you claim
- **C.** `NOTES.md`: what you changed in `prj.conf` and why
- **D.** `@checkpoint`

## Definition of done

You can say what happens if the high-priority thread never sleeps.
You did not "fix" scheduling with a `k_busy_wait` loop as the design.
