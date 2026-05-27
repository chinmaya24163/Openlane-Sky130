# SKY_L3 - From Software Applications to Hardware

## Introduction

This lecture explains the complete software-to-hardware execution flow using real-world application examples.

The lecture describes:

- how applications execute on hardware
- the role of system software
- operating systems
- compilers
- assemblers
- instruction set architecture
- RTL implementation

The lecture builds a bridge between software applications and chip-level hardware execution.

---

# Application Software and Hardware

Applications such as:

- desktop applications
- mobile applications

run on hardware present inside:

- laptops
- desktops
- mobile devices

## How does application software communicate with hardware?

### System Software

Between the application and hardware lies system software, which acts as an intermediate layer. Major components include:

- Operating System (OS)
- Compiler
- Assembler

### Overall Execution Flow

The complete flow:

```text
Application Software
        ↓
System Software (OS, Compiler, Assembler)
        ↓
Binary Machine Code
        ↓
Hardware Execution
```

### Role of the Operating System

The operating system performs several functions such as:

- I/O handling
- memory allocation
- process management
- resource management

Additionally, the OS helps in managing the execution flow of application programs.

### Role of the Compiler

The compiler converts C/C++/Java program into Processor-Specific Instructions. The generated instructions depend on the hardware architecture.

Examples:

| Hardware Architecture | Instruction Format |
|---|---|
| Intel x86 | x86 Instructions |
| ARM | ARM Instructions |
| MIPS | MIPS Instructions |
| RISC-V | RISC-V Instructions |

In our case, compiler output is generated in RISC-V instruction format. The compiler translates high-level programs into architecture-specific instructions.

### Role of the Assembler

The assembler converts instructions into machine language, which consists of binary numbers:

- logic 1
- logic 0

This is the only language understood by hardware.

---

# Hardware Interpretation

The hardware interprets binary patterns and performs operations accordingly. Hardware performs operations based on instruction encoding.

---

# Stopwatch Application Example

## Flow

```text
Stopwatch App
      ↓
C Function
      ↓
Compiler
      ↓
RISC-V Instructions
      ↓
Assembler
      ↓
Binary Machine Code
      ↓
Hardware Execution
      ↓
Expected Stopwatch Behavior
```

This demonstrates how real applications ultimately become binary instructions executed by hardware.

---

# Instruction Set Architecture (ISA)

The instruction set acts as an abstract interface between software and hardware. ISA defines:

- instructions
- syntax
- operations
- communication method with hardware

Thus ISA is often called Architecture of the Computer.

---

# ISA as Human-Hardware Interface

ISA acts as the language between human and computer. Users write programs, indirectly communicating with hardware through ISA instructions.

---

# Hardware Description and RTL

The hardware itself must be designed to understand instruction patterns. This requires:

## RTL (Register Transfer Level)

RTL:

- implements ISA specifications
- describes hardware behavior
- defines datapath and control logic

## ISA vs RTL

### ISA

ISA defines WHAT the processor should do. It is the specification.

### RTL

RTL defines HOW the processor is implemented. It is the hardware implementation.

## RTL to Netlist

RTL is synthesized into:

### Netlist

A netlist consists of:
- logic gates
- flip-flops
- interconnections

This forms the lower-level hardware representation used for physical design.

---

# Expanded Complete Flow

```text
Application Software
        ↓
Operating System
        ↓
Compiler
        ↓
RISC-V Instructions (ISA)
        ↓
Assembler
        ↓
Binary Machine Code
        ↓
RTL Implementation
        ↓
Netlist
        ↓
Chip Hardware
        ↓
Program Execution
```

---

# Key Takeaways

- Applications execute on processor hardware.
- System software bridges software and hardware.
- Operating system manages resources and execution.
- Compiler converts programs into architecture-specific instructions.
- Assembler converts instructions into binary machine code.
- Hardware understands only binary signals.
- ISA acts as the interface between software and hardware.
- RTL implements ISA specifications.
- RTL is synthesized into gate-level netlists.
