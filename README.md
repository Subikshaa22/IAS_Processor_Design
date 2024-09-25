# EG 212 Computer Architecture – IAS Processor Design 

## Project Overview

This project implements an IAS (Instructional Automatic Sequencing) processor, a simplified machine that mimics the architecture of the original IAS computer. The primary objectives include implementing a C program for solving a problem, writing an assembly program for the C code, introducing new instructions, and designing a functioning assembler and processor. The program is tested using a quadratic equation example, and we have incorporated additional assembly instructions for discriminant calculation and square root extraction.

### Key Features

- **C and Assembly Programming**: The C program solves a quadratic equation, and its corresponding assembly program uses IAS architecture.
- **Assembler**: Converts IAS assembly language into machine code.
- **Processor Design**: Simulates the instruction cycle (fetch, decode, execute) of the IAS machine.
- **Custom Instructions**: Two new instructions (`DISC` and `SQRT`) have been added to calculate the discriminant and the square root in the assembly program.
- **Step-by-Step Instruction Cycle**: Implements the entire instruction cycle, including memory operations and ALU instructions.

---

## Project Components

### 1. **C Program**
The C program chosen for this project solves a quadratic equation of the form:
$$ ax^2 + bx + c = 0 $$
It calculates the discriminant to determine whether the roots are real. If the discriminant is positive, the program calculates the real roots.

### 2. **Assembly Program**
The assembly program is based on IAS architecture and includes the following operations:

- **Load and Store Instructions**: To move data between memory and registers.
- **ALU Instructions**: Includes addition and multiplication operations required for discriminant and root calculations.
- **Jump Instructions**: Used for branching based on the value of the discriminant.
- **Custom Instructions**:
  - **DISC**: Calculates the discriminant `b^2 - 4ac`.
  - **SQRT**: Calculates the square root of the discriminant if it is positive.

### 3. **Assembler**
The assembler reads the IAS assembly code, converts it into machine code, and verifies the generated machine code using the IAS instruction set. It consists of three main functions:

1. **`opcode()`**: Returns the opcode of the given instruction.
2. **`convert_binary()`**: Converts decimal integers into binary.
3. **`mach_lang_prog()`**: Converts assembly instructions into machine language and stores them in memory.

### 4. **Processor Design**
The processor is designed to simulate the IAS machine and includes:

- **Instruction Fetch**: Fetches the next instruction from memory using the Program Counter (PC).
- **Instruction Decode**: Decodes the fetched instruction to determine the operation and operands.
- **Instruction Execute**: Executes the instruction step-by-step, including ALU operations, memory reads, and writes.
  
#### Key Components:
- **AC (Accumulator)**: Stores the result of arithmetic operations.
- **MQ (Multiplier-Quotient)**: Used for multiplication and division.
- **MAR (Memory Address Register)**: Stores memory addresses for fetching data.
- **MBR (Memory Buffer Register)**: Holds the data fetched from memory.
- **PC (Program Counter)**: Holds the address of the next instruction.

The program simulates the IAS processor's instruction cycle and executes the assembled machine code by fetching, decoding, and executing instructions one-by-one. The design includes a `my_operation()` function that handles individual operations and a `decode_instruction()` function that breaks down each instruction cycle.
