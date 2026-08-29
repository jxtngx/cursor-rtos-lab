# Lessons

Lesson 00 is C on the host.
Lessons 01–12 are Zephyr, **required** to pass on `native_sim` (and QEMU where named).
S1 and S2 are supplementary. They do not replace 00–12.

You write every application.
Agents open `LESSON.md`, quiz you, and review.
They do not implement.

| # | Folder | Spine | Run |
| --- | --- | --- | --- |
| 00 | [00-c-basics](00-c-basics/LESSON.md) | C17, gcc | host |
| 01 | [01-west-sim](01-west-sim/LESSON.md) | west, native_sim | native_sim |
| 02 | [02-threads](02-threads/LESSON.md) | threads | native_sim ztest |
| 03 | [03-scheduling](03-scheduling/LESSON.md) | scheduling | native_sim ztest |
| 04 | [04-sync](04-sync/LESSON.md) | sem, mutex, poll | native_sim ztest |
| 05 | [05-timers-workqueues](05-timers-workqueues/LESSON.md) | timers, workqueue | native_sim ztest |
| 06 | [06-interrupts](06-interrupts/LESSON.md) | interrupts | native_sim / QEMU |
| 07 | [07-memory](07-memory/LESSON.md) | stacks, heap, slabs | native_sim ztest |
| 08 | [08-devicetree](08-devicetree/LESSON.md) | DT | native_sim |
| 09 | [09-kconfig-cmake](09-kconfig-cmake/LESSON.md) | Kconfig, CMake | native_sim + qemu_cortex_m3 |
| 10 | [10-drivers-sim](10-drivers-sim/LESSON.md) | UART, GPIO | native_sim |
| 11 | [11-ztest-twister](11-ztest-twister/LESSON.md) | ztest, twister | both platforms |
| 12 | [12-firmware](12-firmware/LESSON.md) | capstone | both platforms |
| S1 | [S1-boards-shields](S1-boards-shields/LESSON.md) | boards, shields | NOTES + overlay you wrote |
| S2 | [S2-bench-id-print](S2-bench-id-print/LESSON.md) | bench, ID, TAA/NDAA AM | NOTES + CAD you wrote |

## How to start

1. Read the official links
2. `@start-lesson 00`
3. `@review-firmware` after tests are green
4. `@checkpoint`

## What must not happen

- An agent filling `src/`
- A copied Zephyr sample as the lesson body
- A physical board as a requirement for 00–12
