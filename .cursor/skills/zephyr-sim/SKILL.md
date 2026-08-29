---
name: zephyr-sim
description: Zephyr native_sim and QEMU. Use when building, running, or testing core lessons without hardware.
---

# Simulator path

- Board: `native_sim` — https://docs.zephyrproject.org/latest/boards/native/native_sim/doc/index.html
- QEMU default: `qemu_cortex_m3`
- Tests: ztest + `west twister -p native_sim`
- Out-of-tree apps: https://docs.zephyrproject.org/latest/develop/application/index.html

West workspace is beside this git repo, not inside it.
Do not implement the student's app.
