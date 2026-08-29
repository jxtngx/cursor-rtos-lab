# Lesson 00 — C basics

> Spine: C17 · [cppreference/c](https://en.cppreference.com/w/c) · host `gcc`
> Concept: firmware is C with a kernel. If you cannot explain a pointer and a translation unit on the host, Zephyr will only hide that.
> Run: **host gcc**. No west yet.

## Contract

The tutor may name the flag (`-std=c17`, `-Wall -Wextra -Werror`).
The tutor may not write your programs or your test driver.

## Read first

- [ ] Compilation model: `.c` / `.h`, translation units, `static` vs `extern`
- [ ] Types: `stdint.h`, `size_t`, why `int` is the wrong default width
- [ ] Pointers, arrays, strings (`'\0'`), structs, enums
- [ ] Storage duration: automatic, static, allocated (`malloc` / `free`)
- [ ] `const` and `volatile` (you will need `volatile` for MMIO later)
- [ ] Undefined behavior you can trigger on purpose (use-after-free or signed overflow) and then stop doing it
- [ ] `gcc -g` and a one-page gdb cheat you wrote yourself

## Plan of work

- **A. Read first**
- **B.** Tiny layout: `src/`, headers, a `Makefile` or script **you** write
- **C.** Host tests you write (a `main` that returns non-zero on failure is enough):
  - pointer vs array decay
  - struct by value vs by pointer
  - a `static` counter with internal linkage
- **D.** One program that demonstrates `volatile` (compiler must not delete a store/load you can show in `-O2` assembly or explain in `NOTES.md`)
- **E.** `NOTES.md`: last warning you turned into a fix; one UB you will not ship
- **F.** `@checkpoint`

## You write

`lessons/00-c-basics/` C sources and tests. C17. No C++. No Zephyr headers yet.

## Definition of done

You can write a two-file program (`.c` + `.h`) from a blank directory and explain every `*` in it.
You did not "learn C" by pasting a kernel sample.
