# textkit — Preparing for Systems Programming with C

This repository contains **textkit**, a small command-line utility written in C that I am building while working through **_The C Programming Language (Kernighan & Ritchie, 2nd Edition)_**.

The primary goal of this project is **to be prepared for a systems programming course**, not to build a fully polished tool upfront.

This project is intentionally **incremental, constrained, and learning-focused**.

---

## Project Goals (Short-Term)

**Before the semester starts (2–3 weeks):**
- Become fluent with basic C syntax and control flow
- Understand functions, headers, and multi-file programs
- Gain *real exposure* to pointers and arrays
- Write, debug, and refactor real C code
- Be able to follow systems programming lectures without panic

**During the semester:**
- Continue extending `textkit`
- Deepen understanding of pointers, structs, and I/O
- Refactor code as new concepts are learned in class

---

## What `textkit` Is

`textkit` is a small Unix-style text utility inspired by tools like:
- `wc` (word/line/character counting)
- `grep` (pattern matching)
- simple word-frequency analysis

The project grows **only as new concepts are learned** — no features are added prematurely.

---

## Scope and Constraints

To stay focused and realistic:

- Early chapters may use a **single file**
- No external libraries or frameworks
- No premature optimization
- No dynamic memory until the book introduces it
- Correctness and understanding matter more than feature count

---

## Chapter Roadmap (Pre-Semester Focus)

### Chapter 1 — A Tutorial Introduction
**Objective:** Write and understand a complete C program.

**Features**
- Read text from standard input
- Count characters, words, and lines
- Print results to standard output

**Key Concepts**
- `main`
- loops
- `getchar`
- `printf`

---

### Chapter 2 — Types, Operators, Expressions
**Objective:** Think precisely about data and conditions.

**Features**
- Count digits, whitespace, and other characters
- Use appropriate numeric types (`int`, `long`)
- More detailed output

---

### Chapter 3 — Control Flow
**Objective:** Control program behavior using arguments and branching.

**Features**
- Basic command-line flags (`-l`, `-w`, `-c`)
- Manual parsing of `argv`
- Graceful handling of invalid input

---

### Chapter 4 — Functions and Program Structure
**Objective:** Write maintainable, modular C programs.

**Features**
- Break logic into reusable functions
- Split code into multiple `.c` and `.h` files
- Separate input handling from computation

📌 This chapter marks the transition from “toy programs” to real C programs.

---

### Chapter 5 — Pointers and Arrays (Critical)
**Objective:** Build a correct mental model of memory.

**Features**
- Rewrite string and input logic using pointers
- Pass arrays and strings to functions correctly
- Debug pointer-related bugs intentionally

📌 Mastery is not expected here — **exposure and reasoning are the goal**.

---

## Implementation Guidance (High-Level)

These notes guide *how to think*, not what to copy.

### Input Handling
- Start with character-by-character input
- Use fixed-size buffers
- Avoid dynamic allocation until later

### Program Structure
- Let structure emerge naturally
- Refactor only when complexity demands it
- Keep responsibilities clear and narrow

### Debugging
- Expect bugs, especially with pointers
- Use compiler warnings aggressively
- Reason about memory instead of guessing

---

## Build & Run

Early chapters:
```bash
gcc main.c -o textkit
./textkit
