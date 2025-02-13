# Pipelined MIPS Processor Implementation

This project implements a **16-bit MIPS-like processor** with seven 16-bit general-purpose registers (R1 through R7) and one 12-bit program counter (PC). R0 is hardwired to zero and cannot be written. The processor supports a pipelined architecture with forwarding logic, hazard detection, and stalling mechanisms.

## Features
- **16-bit Instruction Set**: Supports R-type, I-type, LW, SW, branch, and jump instructions.
- **Pipeline Architecture**: Implements a 5-stage pipeline (IF, ID, EX, MEM, WB) with forwarding and hazard handling.
- **Testing and Verification**: Includes comprehensive testing for all instructions, data dependencies, and pipeline hazards.
- **Custom Compiler**: A custom compiler translates assembly code into machine code (hexadecimal format) for simulation in Logisim.

---

## Table of Contents
- [Phases](#phases)
  - [Phase 1: Single-Cycle Processor](#phase-1-single-cycle-processor)
  - [Phase 2: Pipelined Processor](#phase-2-pipelined-processor)
- [Testing and Verification](#testing-and-verification)
- [Usage](#usage)
- [Compiler](#compiler)
- [License](#license)
- [Contact](#contact)

---

## Phases

### Phase 1: Single-Cycle Processor
- **Objective**: Build the datapath and control logic for a single-cycle processor.
- **Components**:
  - ALU
  - Register File
  - Control Unit
  - Instruction Memory
  - Data Memory
- **Testing**: Verify the correctness of each component independently before integrating them.

### Phase 2: Pipelined Processor
- **Objective**: Extend the single-cycle design to a pipelined architecture.
- **Features**:
  - **Forwarding Logic**: Handle data dependencies between instructions.
  - **Hazard Detection**: Stall the pipeline after a `LW` instruction if followed by a dependent instruction.
  - **Branch Handling**: Manage control hazards for branch and jump instructions.
- **Testing**: Verify the correctness of the pipeline by testing sequences of dependent instructions and branch behaviors.

---

## Testing and Verification

### Component Testing
- Test each component (ALU, Register File, Control Logic, etc.) independently to ensure correctness.
- Verify the execution of all instructions (R-type, I-type, LW, SW, branches, and jumps).

### Pipeline Testing
- Test sequences of dependent instructions to validate forwarding logic.
- Verify stalling behavior after a `LW` instruction.
- Test taken and untaken branch instructions to ensure correct pipeline behavior.

### Test Programs
- Write assembly programs to test all instructions and scenarios.
- Use the custom compiler to translate assembly code into machine code (hexadecimal format) for simulation in Logisim.

---

## Usage

### Compiler
- The custom compiler translates assembly code into machine code (hexadecimal format) for simulation in Logisim.
- **Steps**:
  1. Write your assembly code in a text file.
  2. Use the compiler to assemble the code into hexadecimal format.
  3. Load the hexadecimal instructions into the instruction memory in Logisim.

### Simulation in Logisim
1. Load the instruction memory with the compiled hexadecimal code.
2. Load the data memory with initial data (if required).
3. Run the simulation and observe the register values (R1 to R7) at the top level.

