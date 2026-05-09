

# 16-Bit Basic Computer Simulation 💻⚙️

A complete Logisim implementation of a basic computer architecture, featuring a custom memory system, Arithmetic Logic Unit (ALU), and a hardwired Control Unit. This project was developed as part of the CSEN/CSIS402: Computer Organization and Systems Programming course.


<img width="1280" height="776" alt="SimulationVod-ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/1565bc36-214b-4fd0-8951-2b28ebc4a147" />



## 📋 Table of Contents
- [About the Project](#about-the-project)
- [Architecture & Features](#architecture--features)
- [Supported Instructions](#supported-instructions)
- [Getting Started](#getting-started)
- [File Structure](#file-structure)

## 🔍 About the Project

This project simulates the cycle-by-cycle execution of machine instructions. It is designed around a common bus architecture with 3 control select lines. The system successfully executes a custom assembly program by fetching, decoding, and executing instructions through micro-operations governed by a Sequence Counter and Decoders. 

## ✨ Architecture & Features

* **Memory (RAM):** 128-word address space, with each word being 16-bits.
* **Registers:** Includes AR, PC, DR, AC, IR, and TR. Built with a D-Flip Flop mechanism to enforce synchronous clear signals.
* **Common Bus System:** Multiplexer/Encoder-based bus routing data between memory and registers.
* **Arithmetic Logic Unit (ALU):** Performs operations between the Data Register (DR) and Accumulator (AC). Supported operations include:
  * Transfer Input A
  * Increment
  * Addition (`A + B`)
  * Subtraction (`A - B`)
  * Multiplication (`A * B`)
  * Division (`A / B`)
  * Bitwise XOR

## 📜 Supported Instructions

The hardwired Control Unit supports the following Instruction Set Architecture (ISA):
* `LDA` - Load Accumulator
* `STA` - Store Accumulator
* `ADD` - Add to Accumulator
* `MUL` - Multiply with Accumulator
* `DIV` - Divide with Accumulator
* `ISZ` - Increment and Skip if Zero
* `BUN` - Branch Unconditionally

## 🚀 Getting Started

### Prerequisites
* [Logisim](http://www.cburch.com/logisim/) (Requires Java runtime)

### Running the Simulation
1. Clone the repository to your local machine.
2. Open the Logisim application.
3. Navigate to `File > Open` and select `Main Circuit.circ`.
4. Right-click on the Memory (RAM) module in the circuit and select **Load Image...**.
5. Select the `Memory Values` file to load the machine code for the test program.
6. Go to `Simulate` in the top menu:
   * Select **Ticks Enabled** (Ctrl+K) to run continuously.
   * Or use **Tick Half-Cycle** (Ctrl+T) to manually step through the RTLS clock-by-clock.

## 📁 File Structure

* `Main Circuit.circ`: The top-level circuit tying all components together.
* `ALU.circ`: The Arithmetic Logic Unit circuitry.
* `Control Unit.circ`: Hardwired logic mapping execution timings to control signals.
* `Encoder.circ`: Handles the selection lines for the common bus.
* `SC.circ`: The Sequence Counter for timing generation.
* `Modified Register.circ` / `Modified Counter.circ`: Custom register designs implementing synchronous clears.
* `Memory Values`: Text file containing the pre-compiled machine code.
* `RTLs.pptx` & `Project Report.pdf`: Documentation of the boolean expressions and Register Transfer Logic.
