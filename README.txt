CS211 - Programming Assignment 4
================================

Project Title: Logic Circuit Truth Table Generator

Author: JiuChongZiYue
Course: CS211 - Fall 2022
Assignment: PA4
Due Date: December 12, 2022

Overview
--------

This project involves writing a C program named `truthtable` that reads a textual description of a
digital logic circuit and prints out the corresponding truth table. The project emphasizes working
with logical gates, parsing formatted input files, and simulating digital logic to produce output.

The project includes:
- Reading circuit specifications from file
- Building internal representations of circuits using appropriate data structures
- Generating and printing truth tables row-by-row
- Optional: Handling unsorted gates (extra credit)

Program Description
-------------------

Program Name: `truthtable`

- Input: A file containing a digital logic circuit specification
- Output: The full truth table of the circuit, one row at a time
- Input and output variables are displayed in order and separated by a pipe `|`

Supported Gates:
- AND, OR, NOT, NAND, NOR, XOR
- DECODER (n-to-2^n)
- MULTIPLEXER (2^n-to-1)
- PASS (used to convert intermediate values to output)

Usage
-----

    ./truthtable <circuit_file>

Example:

    ./truthtable my_circuit.txt

    Output:
    0 0 0 | 0
    0 0 1 | 0
    ...
    1 1 1 | 1

Specification Format
--------------------

The input file must begin with:
- `INPUT n var1 var2 ... varN`
- `OUTPUT m out1 out2 ... outM`

Then followed by any number of gate directives (e.g., AND, OR, DECODER, etc.).

Temporary/intermediate variables are allowed and are automatically tracked.

Build & Compilation
-------------------

Directory Structure:

    src/
    ├── Makefile
    └── truthtable.c

To compile:

    make

To clean:

    make clean

Makefile Requirements:
- Must compile `truthtable.c` with flags `-g -std=c99 -Wall -Wvla -Werror -fsanitize=address,undefined`

Testing
-------

- Truth tables are printed one row at a time to handle large input sizes.
- Use the provided `grader.py` tool to check correctness and grading feedback.
- Auto-grader will test both sorted and unsorted circuit descriptions.

Implementation Notes
--------------------

- Use `fscanf` with `%16s` to read tokens safely
- Use integers to represent variable IDs for fast array indexing
- Use efficient simulation for gate evaluation (not full truth table storage)

Extra Credit
------------

Part 2: Handle circuits with unsorted gate order (i.e., dependency resolution required)

Academic Integrity
------------------

This work was completed individually in accordance with the course’s academic integrity policy.
