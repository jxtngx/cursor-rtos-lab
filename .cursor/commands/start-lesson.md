# Start Lesson

Open the next RTOS lesson. Teach one official concept. Do not write the student's firmware.

## Usage

```
@start-lesson [00-12 | S1 | S2 | slug]
```

## MUST

1. Open `lessons/.../LESSON.md`
2. Confirm **Read first**
3. State the one concept
4. Ten to twenty lines of the *concept*, never the finished app
5. Point at **Plan of work** and stop

## MUST NOT

- Create `src/` or `prj.conf` that implement the exercise
- Copy Zephyr samples
- Require a physical board for 00–12
