# Lesson 09 — Kconfig and CMake

> Spine: [Kconfig](https://docs.zephyrproject.org/latest/build/kconfig/index.html) · [Application](https://docs.zephyrproject.org/latest/develop/application/index.html)
> Concept: `prj.conf` is a product choice. CMake is how the app exists out-of-tree.
> Run: `native_sim` and `qemu_cortex_m3` **builds** of the same app.

## Read first

- [ ] `CONFIG_*` in `prj.conf` vs `Kconfig` you add
- [ ] `find_package(Zephyr)` application CMake
- [ ] `CONF_FILE` / extra conf fragments

## Plan of work

- **A. Read first**
- **B.** App Kconfig symbol you invent (`CONFIG_LAB_*`) that changes a string or a buffer size
- **C.** Tests or a print that prove the symbol worked
- **D.** Build both boards. `NOTES.md` with both commands
- **E.** `@checkpoint`

## Definition of done

You can add a Kconfig symbol without editing Zephyr's tree.
