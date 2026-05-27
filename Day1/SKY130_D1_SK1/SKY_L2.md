# SKY_L2 - Introduction to RISC-V

## Introduction

This lecture introduces the concept of:

- RISC-V Instruction Set Architecture (ISA)
- How software communicates with hardware
- The flow from a C program to chip execution
- Relationship between ISA, RTL, and physical layout

The instructor explains how a high-level software program eventually gets executed inside the processor hardware.

---

# Instruction Set Architecture

ISA stands for Instruction Set Architecture. It defines:

- how software communicates with hardware
- the instruction formats
- operations supported by the processor
- behavior of the CPU

RISC-V is an open-source ISA.

---

# Flow of Program Execution

The lecture explains the complete flow of how a C program gets executed on hardware.

The flow is:

```text
C Program
   ↓
RISC-V Assembly Program
   ↓
Machine Language Program (Binary Bits - 1s and 0s)
   ↓
Executed on Hardware Layout
```

## Step 1 - C Program

The process starts with a high-level C program. The program is written in a human-readable format.

## Step 2 - Assembly Language Program

The C program is compiled into RISC-V Assembly Language. Assembly language consists of:

- low-level instructions
- architecture-specific operations
- processor instructions understandable by the ISA

## Step 3 - Machine Language Program

The assembly instructions are then converted into Machine Language. Machine language consists of:

- binary instructions
- logic 0s and logic 1s
- electrical signals understood by hardware

---

# Step 4 - Execution on Hardware

The binary instructions are executed on the processor hardware layout. As a result:

- the desired computation gets performed
- output is generated

---

# Hardware Description Language (HDL)

Between the RISC-V architecture and the physical hardware implementation, another layer exists:

## RTL / Hardware Description Language

RTL stands for Register Transfer Level. RTL is used to implement the ISA specifications in hardware.

---

# Relationship Between ISA and RTL

ISA is the specification. The ISA defines what the processor should do. RTL is the implementation. RTL defines how the processor is actually built. The RTL implements the RISC-V ISA specifications.

---

# RTL to Layout Flow

After RTL design, the chip goes through:

## RTL-to-GDSII Flow

This includes:
- synthesis
- floorplanning
- placement
- clock tree synthesis
- routing
- physical verification

This entire process is called Physical Design Flow or RTL-to-GDSII Flow.

---

# Complete Chip Design Flow

The complete flow:

```text
RISC-V ISA
     ↓
RTL Implementation
     ↓
RTL-to-GDSII Flow
     ↓
Chip Layout
     ↓
Program Execution on Hardware
```

---

# User Perspective

From the user's point of view:

- they simply run an application
- the underlying hardware automatically executes the instructions
- the processor performs the required computation internally

The complexity of:
- ISA
- RTL
- layout generation
- hardware implementation

remains hidden from the end user.

---

# Key Takeaways

- RISC-V is an open-source ISA.
- ISA acts as the language between software and hardware.
- C programs are converted into assembly instructions.
- Assembly instructions become machine-level binary instructions.
- Binary signals are executed by processor hardware.
- RTL implements ISA specifications.
- RTL is converted into chip layout using physical design flow.
- Hardware execution remains transparent to end users.