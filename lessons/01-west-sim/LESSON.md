# Lesson 01 — West and simulators

> Spine: [Getting Started](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) · [native_sim](https://docs.zephyrproject.org/latest/boards/native/native_sim/doc/index.html) · [Application development](https://docs.zephyrproject.org/latest/develop/application/index.html)
> Concept: west builds an **out-of-tree** app onto a **simulated** board. The simulator is the lab bench for 01–12.
> Run: `native_sim`. Optional: `qemu_cortex_m3` as a second build.

## Read first

- [ ] west init / update / sdk (workspace **beside** this git repo)
- [ ] `west build -b native_sim` and `west build -t run`
- [ ] Why `native_sim` is a POSIX executable and QEMU is not
- [ ] Out-of-tree `CMakeLists.txt` + `prj.conf` + `src/main.c`

## Plan of work

- **A. Read first.** Toolchain check may use upstream `samples/hello_world`. That is **not** your app.
- **B.** Out-of-tree app in this folder that prints a line **you** chose
- **C.** `west build -p always -b native_sim <this-folder>` and run it
- **D.** Same app `west build -b qemu_cortex_m3` (build required; run if your host can)
- **E.** `NOTES.md`: west workspace path, SDK version, both command lines
- **F.** `@checkpoint`

## You write

The application. Do not commit `build/`.

## Definition of done

You can recreate the app from an empty folder and run it on `native_sim` without a board on the desk.
