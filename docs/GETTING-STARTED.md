# Getting started

1. Open this repo in Cursor so `.cursor/` loads.
2. Host `gcc` with C17 (lesson 00).
3. Follow [Zephyr Getting Started](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) into a **west workspace beside this lab**.
4. Confirm:

```text
west build -p always -b native_sim zephyr/samples/hello_world
```

That sample is a toolchain check. It is not lesson 01's solution.
5. `@start-lesson 00`

## Official docs to keep open

- https://docs.zephyrproject.org/latest/
- https://docs.zephyrproject.org/latest/boards/native/native_sim/doc/index.html
- https://docs.zephyrproject.org/latest/develop/test/ztest.html
- https://docs.zephyrproject.org/latest/develop/twister/index.html
- https://en.cppreference.com/w/c
