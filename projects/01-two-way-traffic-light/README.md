# Two-Way Traffic Light Control System

A two-way traffic light control project implemented for a **Siemens SIMATIC S7-300 PLC**.

## Project Overview

The submitted STEP 7 / SIMATIC Manager report documents a cyclic program in `OB1` for controlling two traffic directions. The logic uses internal memory bits, timers, and output signals to sequence the red, yellow, and green lamps.

## Hardware and Software

| Item | Specification |
|---|---|
| PLC family | Siemens SIMATIC S7-300 |
| CPU | CPU 314C-2 DP |
| Program block | OB1 (Main Program Sweep) |
| Engineering software | STEP 7 / SIMATIC Manager |
| Logic representation | Ladder-style logic in the supplied report |

## I/O Address Reference

The following addresses and labels are taken from the supplied project report.

| Address | Label / Function |
|---|---|
| `I0.0` | Start |
| `I0.1` | Stop |
| `Q0.0` | Red 0 |
| `Q0.1` | Yellow 0 |
| `Q0.2` | Green 0 |
| `Q1.0` | Red 1 |
| `Q1.1` | Yellow 1 |
| `Q1.2` | Green 1 |

## Timing Values Documented

| Timer | Preset shown in report | Associated sequence |
|---|---:|---|
| T1 | 20 s | First direction sequence |
| T3 | 16 s | Second direction sequence |
| T4 | 12 s | Yellow transition in the second direction |
| T6 / T8 | 500 ms | Flashing logic |
| T2 | 16 s | Yellow transition in the first direction |

> **Note:** Timer labels and preset values above are transcribed from the supplied PDF. The original report's network comments and timer references are retained as source documentation; the exact operational sequence should be validated against the original STEP 7 project before being treated as a tested specification.

## Program Organization

The supplied report contains five networks in `OB1`:

1. First direction red/green control and flashing logic.
2. Yellow lamp timing for the first direction.
3. Second direction red/green control and flashing logic.
4. Yellow lamp timing for the second direction.
5. Yellow lamp flashing reference for the second direction.

## Source Document

The original three-page STEP 7 report is included at:

[`docs/original-project.pdf`](docs/original-project.pdf)

## Verification Status

- [x] Original PDF report archived
- [x] Hardware and I/O labels documented from the report
- [ ] Original editable STEP 7 project files added
- [ ] Simulation / hardware test evidence added
- [ ] Sequence and interlocking behavior independently validated

## Portfolio Notes

This repository currently contains the source report and its documentation. It does **not** claim that a PLC simulation or physical commissioning test has been performed.
