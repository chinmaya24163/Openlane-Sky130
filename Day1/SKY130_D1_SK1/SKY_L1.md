# SKY_L1 - Introduction to QFN-48 Package

## Introduction

In this lecture, the instructor introduces the basics of electronic boards, chip packaging, internal chip structure, SoC components, foundries, and Foundry IPs.

---

# Example Electronic Board

A typical electronic board such as an Arduino board contains:

- Processor
- JTAG interface
- QSPI Flash
- I2C EEPROM
- ADC
- SDRAM
- Power and Ground connections

The processor acts as the central component around which all interfaces are connected.

---

# Typical Board Block Diagram

A board can be represented using a block diagram containing:

- Processor
- External memories
- Communication interfaces
- Analog peripherals
- Power connections

The lecture focuses not on embedded system design, but on what exists inside the chip itself.

---

# Chip Packaging

## Package

Example:
- QFN-48 Package
- QFN → Quad Flat No-leads

Other package types also exist with varying:
- pin counts
- dimensions
- form factors

Example:
- QFN-256

## Structure of a Package

A package contains:

- External pins
- Chip mounted at the center
- Wire bonds connecting chip pads to package pins

## Wire Bonds

Wire bonds electrically connect package pins
to  chip boundary pads. This allows signals from the outside world to reach the internal circuitry.

---

# Internal Structure of a Chip

Inside the package lies the actual silicon chip.

Important regions include:

## Pads

Pads are interfaces through which signals enter and exit the chip. They act as connection points between external package pins and internal chip circuitry

## Core

The core region contains the digital logic such as:

- AND gates
- OR gates
- Multiplexers
- Sequential logic
- Other digital circuitry

This is where the actual computation happens.

## Die

The die refers to the complete silicon area of the chip fabricated on the silicon wafer.

---

# Example RISC-V SoC

A sample RISC-V SoC may contain:

- SRAM
- ADC
- DAC
- PLL
- SPI
- Processor Core
- Other peripheral blocks

These blocks together form a complete System-on-Chip (SoC).

---

# Foundry IPs

Blocks such as:

- PLL
- ADC
- DAC
- SRAM

are typically called Foundry IPs.

## Intellectual Property

IP stands for intellectual property. These are highly specialized blocks requiring advanced design expertise.

## What is a Foundry?

A Foundry is:

- a semiconductor manufacturing factory
- a facility containing fabrication machines
- the place where chips are physically manufactured

Examples of foundry operations include:
- Lithography
- Deposition
- Fabrication processes

## Role of Foundry in Chip Design

VLSI engineers continuously interact with the foundry using:
- technology files
- interface files
- process information

These files help designers create layouts compatible with the manufacturing process.

---

# Macros vs IPs

## Macros

Macros are primarily digital logic blocks.

## Foundry IPs

Foundry IPs are:
- specialized blocks
- process-dependent
- designed using advanced techniques

Examples:
- PLL
- SRAM
- ADC

---

# Key Takeaways

- Electronic systems can be represented using block diagrams.
- The outer chip structure is called a package.
- QFN is a common package type.
- Wire bonds connect package pins to chip pads.
- Pads provide signal connectivity.
- Core region contains digital logic.
- Die refers to the silicon chip area.
- SoCs contain both macros (digital blocks) and Foundry IPs.
- Foundries manufacture chips.
- Designers communicate with foundries using technology/interface files.