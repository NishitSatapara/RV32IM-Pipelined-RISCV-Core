# RV32IM 5-Stage Pipelined RISC-V Processor

## Overview

This project implements a 32-bit RV32IM 5-stage pipelined RISC-V processor using Verilog HDL. The processor is designed to execute instructions through the standard pipeline stages: Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), Memory Access (MEM), and Write Back (WB).

The design focuses on understanding processor architecture, pipelining, hazard handling, datapath design, and control-path implementation. A modular approach has been used to improve readability, scalability, and verification.

---

## Features

* 32-bit RV32IM RISC-V Processor
* 5-Stage Pipeline Architecture
* Modular Verilog HDL Design
* Hazard Detection Unit
* Data Forwarding Logic
* Branch Handling Support
* Separate Instruction and Data Memory
* Register File Implementation
* ALU for Arithmetic and Logical Operations
* Functional Verification through Simulation

---

## Pipeline Architecture

```text
Instruction Fetch (IF)
          ↓
Instruction Decode (ID)
          ↓
Execute (EX)
          ↓
Memory Access (MEM)
          ↓
Write Back (WB)
```

The pipelined architecture allows multiple instructions to be processed simultaneously, improving throughput compared to a non-pipelined design.

---

## Project Architecture

```text
RISC_V_PIPELINED_TOP
│
├── Fetch_Cycle
│   ├── PC_Module
│   ├── Instruction_Memory
│   └── Mux_2_1_32
│
├── Decode_Cycle
│   ├── Control_Unit_1
│   ├── Register_File
│   ├── Sign_Extend
│   └── Mux_2_1_32
│
├── Execute_Cycle
│   ├── ALU
│   ├── Branch_Module
│   ├── Mux_2_1_32
│   └── Mux_4_1_32
│
├── Memory_Cycle
│   └── Data_Memory
│
├── Writeback_Cycle
│
└── Hazard_Unit
```

---

## Major Modules

### Fetch Cycle

Responsible for program counter management and instruction fetching from instruction memory.

### Decode Cycle

Decodes instructions, reads register operands, generates immediate values, and creates control signals.

### Execute Cycle

Performs arithmetic, logical, comparison, address calculation, and branch evaluation operations.

### Memory Cycle

Handles load and store instructions through data memory access.

### Writeback Cycle

Writes the final execution result back to the register file.

### Hazard Unit

Detects instruction dependencies and generates forwarding/control signals to maintain correct pipeline execution.

---

## Hazard Handling

### Data Hazards

Resolved using forwarding paths from later pipeline stages to the Execute stage.

### Control Hazards

Managed through branch evaluation and program counter redirection.

### Forwarding Logic

Reduces unnecessary pipeline stalls by supplying the most recent operand values directly from later stages.

---

## Supported Instruction Categories

* R-Type Instructions
* I-Type Instructions
* Arithmetic Instructions
* Logical Instructions
* Immediate Instructions
* Load Instructions
* Store Instructions
* Branch Instructions
* Jump Instructions

---

## Verification

The processor was verified using functional simulation.

Test cases included:

* Arithmetic Operations
* Logical Operations
* Immediate Instructions
* Load and Store Operations
* Branch Instructions
* Hazard Scenarios
* Forwarding Verification

Simulation results confirmed correct instruction execution and pipeline behavior.

---

## Learning Outcomes

Through this project, the following concepts were explored:

* Computer Architecture
* RISC-V ISA
* Verilog HDL Design
* Pipeline Implementation
* Datapath and Control Path Design
* Hazard Detection and Resolution
* Register File Design
* ALU Design
* Memory Interface Design

---

## Future Improvements

* Cache Integration
* Branch Prediction
* FPGA Deployment
* RTL-to-GDSII Flow
* Performance Optimization
* Advanced RISC-V Extensions

---

## Technologies Used

* Verilog HDL
* RISC-V ISA
* Digital Design
* Computer Architecture
* Functional Simulation

---

## License

This project is released under the MIT License.


