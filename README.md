# RISC-V Soft-Core Processor on FPGA using Open-Source Tools Only

This repository contains the final project for the Electrical and Computer Engineering program at Ben-Gurion University. The project demonstrates the implementation of a custom RISC-V soft-core processor on the Lattice iCEBreaker FPGA, using only free and open-source tools.

## 🧠 Project Overview

The goal of the project was to design, implement, and test a RISC-V compatible CPU entirely from scratch, using Verilog and open-source FPGA toolchains. The processor supports RV32I instruction set and includes:
- Multi-cycle core synthesized on FPGA
- Pipelined and optimized pipelined cores simulated in Verilator
- Full toolchain: synthesis, place & route, bitstream generation, simulation, and programming—all without proprietary software

## 🛠️ Technologies and Tools Used

| Category           | Tools                              |
|--------------------|------------------------------------|
| Synthesis          | Yosys                              |
| Place & Route      | Nextpnr                            |
| Bitstream Tools    | IceStorm (`icepack`, `iceprog`)    |
| Simulation         | Icarus Verilog, GTKWave, Verilator |
| Board Control      | Apio                               |
| Development        | Amaranth HDL (partial)             |
| Compilation        | `riscv32-unknown-elf-gcc`          |

## 🧱 FPGA Platform

- **Board**: Lattice iCEBreaker
- **FPGA**: iCE40UP5k (5,280 logic cells, ~13KB BRAM)
- **Peripherals**: UART, 3 buttons, 5 LEDs, SPI Flash (16MB)

## 📐 Architecture Overview

### Implemented Cores:
1. **Multi-Cycle Core**
   - RV32I instruction set
   - Finite State Machine (FSM)-based design
   - Deployed on real FPGA

2. **5-Stage Pipelined Core**
   - IF, ID, EX, MEM, WB stages
   - Simulated in Verilator

3. **Optimized Pipelined Core**
   - Register forwarding
   - Static and dynamic branch prediction

### ISA Support
- Arithmetic: ADD, SUB, AND, OR, XOR, SLT, etc.
- Memory: LB, LH, LW, SB, SH, SW
- Control: BEQ, BNE, JAL, JALR, etc.

## 🧪 Test Programs and Demos

Compiled in C and Assembly and executed on the core (on FPGA or via Verilator):
- ✅ Hello World (UART output)
- 🔢 π digits (Bellard algorithm)
- 🌀 Mandelbrot set visualization
- 🍩 ASCII 3D Donut
- 🔒 AES-128 Encryption

