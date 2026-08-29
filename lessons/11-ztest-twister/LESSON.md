# Lesson 11 — ztest and twister

> Spine: [ztest](https://docs.zephyrproject.org/latest/develop/test/ztest.html) · [Twister](https://docs.zephyrproject.org/latest/develop/twister/index.html)
> Concept: twister is how Zephyr CI thinks. Your app needs `testcase.yaml` (or `tcyaml`) you can explain.
> Run: `west twister -p native_sim -p qemu_cortex_m3` on **this** lesson.

## Read first

- [ ] `ZTEST_SUITE`, `ZTEST`, assertions
- [ ] `testcase.yaml`: platform allow, tags, extra args
- [ ] twister output directory (gitignored)

## Plan of work

- **A. Read first**
- **B.** At least two tests in a suite (happy path + a failure you catch)
- **C.** `testcase.yaml` that allows `native_sim` and `qemu_cortex_m3`
- **D.** Paste the twister summary in `NOTES.md`
- **E.** `@checkpoint`

## Definition of done

You can run twister from the lesson folder (or with `-T`) and read a FAIL as yours, not "the harness is broken."
