# 🚦 Adaptive 4-Way Traffic Light Controller: RTL to Physical Design

## Overview

This project implements an Adaptive 4-Way Traffic Light Controller using Verilog HDL and demonstrates the complete digital ASIC design flow from RTL development to physical implementation.

The controller is designed as a Moore Finite State Machine (FSM) that manages traffic signals for North-South and East-West directions. A traffic density input dynamically adjusts the green-light duration, allowing the controller to respond to changing traffic conditions while maintaining safe signal transitions.

In addition to RTL design and verification, the project was synthesized using Cadence Genus and physically implemented using Cadence Innovus to gain hands-on experience with industry-standard ASIC design tools.

---

## Key Features

* Moore FSM-based traffic light controller
* Adaptive green-light timing using traffic density input
* Dedicated yellow-light transition states for safe operation
* Functional verification using a custom Verilog testbench
* Gate-level synthesis using Cadence Genus
* Physical design implementation using Cadence Innovus
* Area and power analysis during physical implementation

---

## Design Specification

### Signal Encoding

| Signal | Encoding |
| ------ | -------- |
| GREEN  | `2'b10`  |
| YELLOW | `2'b01`  |
| RED    | `2'b00`  |

### FSM States

| State | North-South | East-West |
| ----- | ----------- | --------- |
| S0    | GREEN       | RED       |
| S1    | YELLOW      | RED       |
| S2    | RED         | GREEN     |
| S3    | RED         | YELLOW    |

### Timing Parameters

| Parameter  | Value    |
| ---------- | -------- |
| GREEN_LOW  | 5 cycles |
| GREEN_HIGH | 9 cycles |
| YELLOW_DUR | 3 cycles |

The controller extends the green-light duration when high traffic density is detected and reverts to normal timing under low-density conditions.

---

## RTL Design

The controller follows a 3-block Moore FSM architecture:

### Sequential Logic

* State register
* Timer register

### Next-State Logic

* State transition control
* Timer management
* Density-based timing control

### Output Logic

* Traffic signal generation
* State-based output mapping

---

## Functional Verification

The RTL design was verified using a dedicated Verilog testbench covering:

* Reset functionality
* Low-density traffic scenarios
* High-density traffic scenarios
* State transitions
* Adaptive timing behavior
* Mid-operation reset recovery

Simulation confirmed correct FSM operation and safe traffic signal sequencing under all tested conditions.

---

## Logic Synthesis

After RTL verification, the design was synthesized using Cadence Genus.

Key synthesis activities included:

* RTL elaboration
* Standard-cell mapping
* Gate-level netlist generation
* Timing-driven optimization

The generated gate-level schematic provided insight into how the behavioral Verilog description is transformed into hardware using standard cells.

---

## Physical Design Flow

The synthesized netlist was implemented using Cadence Innovus.

The physical design flow included:

* Floorplanning
* Power Planning (Power Rings and Power Stripes)
* Placement
* Clock Tree Synthesis (CTS)
* Routing
* Area Analysis
* Power Analysis

The project provided practical exposure to the complete RTL → Synthesis → Physical Design workflow used in ASIC development.

---

## Key Learnings

* Designed and verified an FSM-based digital system using Verilog HDL.
* Understood adaptive state-machine implementation techniques.
* Learned RTL-to-Gate-Level transformation using Cadence Genus.
* Gained hands-on experience with the Cadence Innovus physical design flow.
* Explored floorplanning, power planning, placement, CTS, and routing.
* Analyzed implementation metrics such as area and power.
* Connected concepts across Digital Design, Logic Synthesis, and Physical Design.

---

## Tools Used

* Verilog HDL
* Cadence SimVision / Xcelium
* Cadence Genus
* Cadence Innovus

---

## Author

**Saksham Gupta**
Electronics & Communication Engineering
KIET Deemed to be University
