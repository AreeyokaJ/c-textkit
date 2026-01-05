# textkit — Learning C Through a Growing Unix-Style Tool

This repository contains **textkit**, a small command-line utility written in C that I am building **incrementally while working through _The C Programming Language (K&R, 2nd Edition)_**.

The goal of this project is **not** to build something large all at once, but to:
- deeply understand C
- learn Unix-style program design
- practice systems-level thinking
- grow one codebase alongside the book’s chapters

---

## Project Philosophy

- One project, extended chapter by chapter
- Each new feature corresponds directly to concepts learned in the book
- No skipping fundamentals, no frameworks
- Focus on clarity, correctness, and simplicity

This mirrors how real Unix utilities are written and how systems programming is taught.

---

## What `textkit` Will Become

By the end of the book, `textkit` will be a small suite of text-processing tools similar to:

- `wc` (word/line/character counting)
- `grep` (pattern matching)
- word frequency analysis
- file and stdin/stdout support
- proper Unix exit codes
- optional low-level I/O using system calls

---

## Chapter Roadmap

### Chapter 1 — A Tutorial Introduction
**Features**
- Read from standard input
- Count characters, words, and lines
- Print results to stdout

**Concepts**
- `main`
- loops
- `getchar`
- `printf`

---

### Chapter 2 — Types, Operators, Expressions
**Features**
- Count digits, whitespace, and other characters
- Use correct numeric types (`int`, `long`)
- More detailed statistics output

---

### Chapter 3 — Control Flow
**Features**
- Command-line flags (`-l`, `-w`, `-c`)
- Mode selection (e.g. `wc`, `hist`)
- Basic argument parsing via `argv`

---

### Chapter 4 — Functions and Program Structure
**Features**
- Break logic into reusable functions
- Multiple source files (`.c`) and headers (`.h`)
- Cleaner program organization

---

### Chapter 5 — Pointers and Arrays
**Features**
- Rewrite string and input logic using pointers
- Pointer-based iteration instead of indexing
- More efficient text handling

---

### Chapter 6 — Structures
**Features**
- Define structs to represent words and counts
- Store and manage structured data
- Word frequency tracking

---

### Chapter 7 — Input and Output
**Features**
- Read from files as well as stdin
- Handle multiple input files
- Proper error handling for file I/O

---

### Chapter 8 — The UNIX System Interface
**Features**
- Optional low-level I/O (`read`, `write`)
- Unix-style exit codes
- Behavior consistent with real Unix utilities

---

## Implementation Notes (Guided, Not Prescriptive)

The following notes describe *how* each chapter’s features should be approached, without giving full solutions. The intent is to encourage reasoning and reference back to the book.

---

### Chapter 1 — A Tutorial Introduction

**Approach**
- Read input one character at a time from `stdin`
- Detect word boundaries using whitespace
- Increment counters as characters are processed

**Constraints**
- No arrays or pointers yet
- No file input
- No dynamic memory

**Hints**
- Use a state variable to track “inside a word”
- Stop reading on `EOF`

---

### Chapter 2 — Types, Operators, Expressions

**Approach**
- Classify characters using conditionals or `switch`
- Maintain multiple counters simultaneously
- Use appropriate numeric types for large input

**Constraints**
- Continue using character-by-character input
- Avoid library classification functions (e.g. `isdigit`)

**Hints**
- Refer to the digit/whitespace examples in the chapter
- Be careful with operator precedence

---

### Chapter 3 — Control Flow

**Approach**
- Examine `argv` to determine program mode
- Enable or disable output based on flags
- Use branching logic to control execution paths

**Constraints**
- Manual argument parsing (no helper libraries)
- Assume well-formed input initially

**Hints**
- Treat flags as boolean switches
- Handle invalid flags gracefully

---

### Chapter 4 — Functions and Program Structure

**Approach**
- Extract logical units into separate functions
- Introduce header files to share declarations
- Separate input handling from computation

**Constraints**
- No global variables unless necessary
- Keep function interfaces minimal

**Hints**
- Reuse function patterns from K&R (e.g. `getline`)
- Compile with warnings enabled

---

### Chapter 5 — Pointers and Arrays

**Approach**
- Rewrite array-based logic using pointer arithmetic
- Pass pointers instead of array indices
- Manipulate strings directly via pointers

**Constraints**
- Avoid allocating memory dynamically yet
- Use fixed-size buffers

**Hints**
- Remember: array names decay to pointers
- Prefer pointer increment over index math

---

### Chapter 6 — Structures

**Approach**
- Define structs to group related data
- Store word text alongside frequency counts
- Operate on arrays of structs

**Constraints**
- Fixed-size storage initially
- No hash tables yet

**Hints**
- Think about ownership of string data
- Keep struct responsibilities narrow

---

### Chapter 7 — Input and Output

**Approach**
- Add support for file input using `FILE *`
- Process multiple files sequentially
- Fallback to `stdin` when no file is provided

**Constraints**
- One input source at a time
- Clear error messages on failure

**Hints**
- Centralize input logic
- Check return values of all I/O calls

---

### Chapter 8 — The UNIX System Interface

**Approach**
- Introduce an alternative I/O path using system calls
- Use buffered reads for performance
- Return meaningful exit codes

**Constraints**
- Keep stdio-based implementation intact
- Do not mix stdio and low-level I/O in the same path

**Hints**
- Treat file descriptors as integers
- Model behavior after real Unix utilities

---

## Build & Run (will evolve)

```bash
gcc main.c -o textkit
./textkit
