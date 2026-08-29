# Cursor RTOS Lab

Learn **Zephyr RTOS** with SuperGrok and Cursor.
This repo is a **lab**, not a factory.
You read the [official Zephyr docs](https://docs.zephyrproject.org/latest/), you write the C, you sit with `west build` and `west twister` until the kernel service makes sense.
SuperGrok and Cursor are the tutor and the reviewer.
They are not allowed to do the work for you.

> **Audience.** You can type a little C (lesson 00 makes that honest). You intend to go from `printf` to firmware you can explain: threads, sync, timers, devicetree, a driver on a simulator.
> You have [SuperGrok](https://grok.com) and [Cursor](https://cursor.com) open on this repo.
> You will type every function yourself.
>
> **Bias.** Interaction over generation.
> Official Zephyr docs over blog HALs.
> Depth over a pasted sample you cannot recreate.
> **Simulator first.** Core lessons must pass on Zephyr's own emulators.

This is the same contract as [cursor-rust-lab](https://github.com/jxtngx/cursor-rust-lab) and [cursor-robotics-lab](https://github.com/jxtngx/cursor-robotics-lab): a Cursor-native lab where the student does the work.
It is the opposite of a **factory** ([cursor-fullstack-factory](https://github.com/jxtngx/cursor-fullstack-factory), [cursor-agent-factory](https://github.com/jxtngx/cursor-agent-factory), [cursor-deep-learning-factory](https://github.com/jxtngx/cursor-deep-learning-factory), [cursor-swift-factory](https://github.com/jxtngx/cursor-swift-factory)).
If an agent opens a PR with a complete firmware tree you did not write, the lab failed.

The destination is **out-of-tree Zephyr applications** you can rebuild on [`native_sim`](https://docs.zephyrproject.org/latest/boards/native/native_sim/doc/index.html) and at least one **QEMU** board (default: [`qemu_cortex_m3`](https://docs.zephyrproject.org/latest/boards/qemu/cortex_m3/doc/index.html)).
Hardware is stretch, never a gate for lessons 00–12.

---

## What this repo is

A thin Cursor harness around the Zephyr Project.

| Spine | Official thing |
| --- | --- |
| Docs | [docs.zephyrproject.org](https://docs.zephyrproject.org/latest/) |
| Tooling | [west](https://docs.zephyrproject.org/latest/develop/west/index.html) · [Zephyr SDK](https://docs.zephyrproject.org/latest/develop/toolchains/zephyr_sdk.html) |
| Kernel | [Kernel services](https://docs.zephyrproject.org/latest/kernel/services/index.html) |
| Tests | [ztest](https://docs.zephyrproject.org/latest/develop/test/ztest.html) · [twister](https://docs.zephyrproject.org/latest/develop/twister/index.html) |
| Sim | `native_sim` · `qemu_cortex_m3` (and other QEMU boards the lesson names) |
| C | C17 · [cppreference/c](https://en.cppreference.com/w/c) · host `gcc` in lesson 00 |

Lesson **specs** live in [`lessons/`](lessons/README.md). They are not solutions.
This git repo is **not** a west workspace. You `west init` a workspace beside it and point applications at these lesson folders.

What lives here:

- **`lessons/`** — 00 C, 01–12 Zephyr on simulators, **S1** boards/shields, **S2** bench / industrial design / 3D print
- **`.cursor/agents/`** — tutors and reviewers. They explain and quiz. They do not implement.
- **`.cursor/commands/`** — `@start-lesson`, `@explain-concept`, `@review-firmware`, `@checkpoint`
- **`.cursor/rules/`** — student writes the code; official docs; simulator first
- **`.cursor/skills/`** — curriculum, C core, Zephyr sim

## Core lessons (simulator-required)

Full table: [lessons/README.md](lessons/README.md).

| # | Lesson | Spine | Default run |
| --- | --- | --- | --- |
| 00 | [C basics](lessons/00-c-basics/LESSON.md) | C17, gcc | host tests, no west yet |
| 01 | [West and simulators](lessons/01-west-sim/LESSON.md) | getting started, native_sim | `west build -b native_sim` + twister |
| 02 | [Threads](lessons/02-threads/LESSON.md) | kernel threads | native_sim ztest |
| 03 | [Scheduling](lessons/03-scheduling/LESSON.md) | scheduling | native_sim ztest |
| 04 | [Synchronization](lessons/04-sync/LESSON.md) | sem, mutex, poll | native_sim ztest |
| 05 | [Timers and workqueues](lessons/05-timers-workqueues/LESSON.md) | timing, workqueue | native_sim ztest |
| 06 | [Interrupts](lessons/06-interrupts/LESSON.md) | interrupts | native_sim / QEMU ztest |
| 07 | [Memory](lessons/07-memory/LESSON.md) | stacks, heap, slabs | native_sim ztest |
| 08 | [Devicetree](lessons/08-devicetree/LESSON.md) | DT guide | native_sim build + tests |
| 09 | [Kconfig and CMake](lessons/09-kconfig-cmake/LESSON.md) | Kconfig, application | both platforms |
| 10 | [Drivers on sim](lessons/10-drivers-sim/LESSON.md) | UART, GPIO | native_sim |
| 11 | [ztest and twister](lessons/11-ztest-twister/LESSON.md) | ztest, twister | `-p native_sim -p qemu_cortex_m3` |
| 12 | [Firmware you can explain](lessons/12-firmware/LESSON.md) | lessons 02–11 | both platforms |

## Supplementary lessons

Not a substitute for 00–12. Hardware purchase is optional.

| # | Lesson | You produce |
| --- | --- | --- |
| S1 | [Boards and shields](lessons/S1-boards-shields/LESSON.md) | NOTES + a shield skeleton / overlay you wrote |
| S2 | [Bench, industrial design, 3D print](lessons/S2-bench-id-print/LESSON.md) | NOTES + CAD for a TAA/NDAA-aware, publicly documented military AM family |

## How you are supposed to work

```
read the official page  →  write a failing ztest (or host test)  →  ask SuperGrok / Cursor  →  fix *your* C  →  west twister
```

1. Open `lessons/NN-*/LESSON.md` and finish **Read first** before you prompt.
2. Out-of-tree app: you write `CMakeLists.txt`, `prj.conf`, `src/`.
3. Ask SuperGrok or Cursor to explain the linker error or the failed assert, not to paste the kernel sample.
4. Change the code yourself.
5. `@review-firmware` only after tests are green on **native_sim**.
6. `@checkpoint` before moving on.

A useful SuperGrok prompt:

> I read [official URL]. Here is my ztest failure on native_sim. Do not write the fix. Ask me three questions that force the right kernel model.

### What the harness may do

- Point at the exact Zephyr page
- Explain one concept in 10–20 lines, never the finished app
- Review a diff you wrote and refuse copied samples, busy-wait as a scheduler, and "just flash a board" as a skip of the simulator

### What the harness must not do

- Implement `@start-lesson`
- Copy `samples/hello_world` into the lesson folder as your solution
- Require a physical board for 00–12
- Dump a vendor HAL that replaces Zephyr
- Soften threads, races, or devicetree because they are annoying

## Daily loop in Cursor

1. `@start-lesson 00`
2. You create the files the spec names
3. `@explain-concept <idea>` when stuck on *one* idea
4. `@review-firmware` after green tests
5. `@checkpoint`

## Tooling baseline

- **Lesson 00:** `gcc` (C17), `make` or a tiny script, host tests
- **Lessons 01–12:** [Getting Started](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) — west, Zephyr SDK, CMake, Python venv, `dtc`
- Default board: **`native_sim`**
- Second twister platform: **`qemu_cortex_m3`** unless the lesson names another QEMU board
- Open this repo in Cursor so `.cursor/` loads

```text
# west workspace is beside this lab, not inside it
west init -m https://github.com/zephyrproject-rtos/zephyr zephyr-ws
cd zephyr-ws && west update && west packages pip --install && west sdk install
```

## Definition of done for a core lesson

You can do this without the model in the room:

- [ ] Name the official page and the one kernel (or C) concept
- [ ] Tests green on `native_sim` (host gcc for 00)
- [ ] Lesson 11+ also green on `qemu_cortex_m3` when the spec says so
- [ ] You can write the same program from a blank `src/main.c`
- [ ] You did not copy a Zephyr sample as the body of the work

## License

Apache-2.0. See [LICENSE](LICENSE).
Not affiliated with the Zephyr Project.
Official docs remain the source of truth.
