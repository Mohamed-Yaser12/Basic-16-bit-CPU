# 16-Bit Basic Computer Simulation 💻⚙️

A complete Logisim implementation of a basic computer architecture, featuring a custom memory system, Arithmetic Logic Unit (ALU), and a hardwired Control Unit. [cite_start]This project was developed as part of the CSEN/CSIS402: Computer Organization and Systems Programming course at the German University in Cairo [cite: 947-951].

## 📋 Table of Contents
- [About the Project](#about-the-project)
- [Architecture & Features](#architecture--features)
- [Supported Instructions](#supported-instructions)
- [Getting Started](#getting-started)
- [File Structure](#file-structure)

## 🔍 About the Project

This project simulates the cycle-by-cycle execution of machine instructions. [cite_start]It is designed around a common bus architecture with 3 control select lines[cite: 901]. [cite_start]The system successfully executes a custom assembly program by fetching, decoding, and executing instructions through micro-operations governed by a Sequence Counter and Decoders[cite: 957]. 

## ✨ Architecture & Features

* [cite_start]**Memory (RAM):** 128-word address space, with each word being 16-bits[cite: 902].
* [cite_start]**Registers:** Includes AR, PC, DR, AC, IR, and TR [cite: 906-915]. [cite_start]Built with a D-Flip Flop mechanism to enforce synchronous clear signals [cite: 985-987].
* [cite_start]**Common Bus System:** Multiplexer/Encoder-based bus routing data between memory and registers [cite: 901, 1254-1255].
* [cite_start]**Arithmetic Logic Unit (ALU):** Performs operations between the Data Register (DR) and Accumulator (AC) [cite: 918-919]. Supported operations include:
  * [cite_start]Transfer Input A [cite: 920]
  * [cite_start]Increment [cite: 921]
  * [cite_start]Addition (`A + B`) [cite: 925-926]
  * [cite_start]Subtraction (`A - B`) [cite: 923]
  * [cite_start]Multiplication (`A * B`) [cite: 922]
  * [cite_start]Division (`A / B`) [cite: 924]
  * [cite_start]Bitwise XOR [cite: 927]

## 📜 Supported Instructions

[cite_start]The hardwired Control Unit supports the following Instruction Set Architecture (ISA)[cite: 970]:
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
4. [cite_start]Right-click on the Memory (RAM) module in the circuit and select **Load Image...**.
5. [cite_start]Select the `Memory Values` file to load the machine code for the test program[cite: 998].
6. Go to `Simulate` in the top menu:
   * Select **Ticks Enabled** (Ctrl+K) to run continuously.
   * [cite_start]Or use **Tick Half-Cycle** (Ctrl+T) to manually step through the RTLS clock-by-clock .

## 📁 File Structure

* `Main Circuit.circ`: The top-level circuit tying all components together.
* `ALU.circ`: The Arithmetic Logic Unit circuitry.
* `Control Unit.circ`: Hardwired logic mapping execution timings to control signals.
* `Encoder.circ`: Handles the selection lines for the common bus.
* `SC.circ`: The Sequence Counter for timing generation.
* [cite_start]`Modified Register.circ` / `Modified Counter.circ`: Custom register designs implementing synchronous clears [cite: 985-987].
* [cite_start]`Memory Values`: Text file containing the pre-compiled machine code [cite: 998-999].
* [cite_start]`RTLs.pptx` & `Project Report.pdf`: Documentation of the boolean expressions and Register Transfer Logic[cite: 980].
