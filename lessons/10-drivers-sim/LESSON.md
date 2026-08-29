# Lesson 10 — Drivers on the simulator

> Spine: [GPIO](https://docs.zephyrproject.org/latest/hardware/peripherals/gpio.html) · [UART](https://docs.zephyrproject.org/latest/hardware/peripherals/uart.html) · native_sim peripherals on the board page
> Concept: the driver API is the same; the backend is simulated. You still use `DEVICE_DT_GET`.
> Run: `native_sim` ztest. No DK.

## Read first

- [ ] GPIO on `native_sim` (cmdline or documented sim GPIO)
- [ ] UART / console already used by printk — what is extra
- [ ] `gpio_pin_configure_dt` / loopback if the board allows connecting two sim pins

## Plan of work

- **A. Read first**
- **B.** Configure a GPIO (or UART) via DT. Test a write/read or a documented sim hook
- **C.** If loopback is awkward on your SDK revision, test "device ready" + configure and document the sim limitation — still no hardware
- **D.** `NOTES.md`: device node path
- **E.** `@checkpoint`

## Definition of done

You used the Zephyr driver API, not `printf` pretending to be GPIO.
You did not flash a Nucleo to finish this lesson.
