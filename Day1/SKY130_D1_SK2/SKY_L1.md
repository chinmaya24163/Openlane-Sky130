# SKY_L1 - Introduction to all components of open-source digital ASIC design

## Introduction

This lecture introduces:

- OpenLane
- Open-source ASIC design methodology
- Open-source EDA ecosystem
- Process Design Kits (PDKs)
- History of modern ASIC design flow

The lecture explains how modern digital ASICs can now be designed completely using open-source tools and open-source process technologies.

---

# OpenLane

OpenLane is an:

- automated RTL-to-GDSII ASIC flow
- open-source digital ASIC implementation framework 

---

# Major Components Required for ASIC Design

## Hardware Description Language (HDL)

RTL models are required to describe:

- functionality
- digital logic behavior
- IP integration

Examples:

- Verilog
- SystemVerilog
- VHDL

## RTL Models

RTL models are needed for:

- the main design
- all integrated IP blocks

RTL acts as the hardware-level representation of the design.

## EDA Tools

EDA tools perform:

- synthesis
- floorplanning
- placement
- routing
- timing analysis
- verification

These tools automate the ASIC implementation process.

## Process Design Kit (PDK)

The PDK provides:

- fabrication technology information
- device models
- design rules
- standard cell libraries
- IO libraries

The PDK acts as the interface between designers and fabrication facilities.

---

# Open-Source ASIC Design

This includes:
- open-source RTL
- open-source EDA tools
- open-source PDK

## Open-Source RTL Ecosystem

Several open-source RTL repositories already exist. Examples:

- OpenCores
- LibreCores
- GitHub repositories

GitHub contains thousands of Verilog-based projects.

## Open-Source EDA Tools

The lecture mentions several historic and modern open-source EDA tools.

Examples include:

- SPICE
- MAGIC
- SIS
- OpenROAD
- Qflow

Many of these originated from academic research.

## Process Design Kit (PDK)

The PDK contains:

- technology information
- process rules
- device models
- libraries
- fabrication constraints

PDKs are essential for converting designs into manufacturable layouts.

### Contents of a PDK

A PDK typically includes:

- device models
- technology files
- design rules
- standard cell libraries
- IO libraries
- process information

These files are critical for successful chip fabrication.

### Traditional Restrictions on PDKs

Historically:

- PDKs were proprietary
- distributed under NDAs
- inaccessible to students and researchers

This severely limited open ASIC development.

### SkyWater 130nm Open-Source PDK

A major breakthrough occurred when Google + SkyWater released the Sky130 Open-Source PDK, released on June 30, 2020. This became the first widely available open-source PDK. The Sky130 PDK enabled:

- open-source ASIC implementation
- fabrication-ready open hardware
- research accessibility
- educational ASIC development

---

# Evolution of IC Design

Initially chip design and fabrication were tightly coupled inside companies like:

- Intel
- Fairchild
- TI

This period is referred to as "The Age of Gods".

## Mead-Conway Revolution

In 1979, Mead and Conway introduced:

- Lambda-based design rules
- separation of design and fabrication

This revolutionized VLSI design methodology. It enabled:

- fabless companies
- pure-play foundries
- scalable IC education

## Fabless and Pure-Play Model

After the Mead-Conway revolution:

### Fabless Companies

focused on chip design only

### Pure-Play Foundries

focused on fabrication only. The communication interface between the fabless companies and pure play foundries became PDK files and documentation.

---

# Why 130nm Still Matters

Although advanced nodes like:

- 5nm
- 3nm

exist today, 130nm remains important because:

## Lower Fabrication Cost

130nm fabrication is significantly cheaper than advanced nodes.

## Sufficient Performance

Many applications do not require cutting-edge nodes.

130nm still provides:

- good performance
- reasonable frequency
- lower development cost

### Intel Pentium 4

- Fabricated using 130nm technology
- Operated near 3.5 GHz

### Sky130 RISC-V CPU Example

A RISC-V single-cycle CPU implemented on Sky130 achieved clock frequency greater than 300 MHz. A pipelined version could potentially exceed 1 GHz.

---

# ASIC Design Complexity

ASIC implementation involves:
- tens of design stages
- multiple EDA tools
- complex methodologies

A complete design flow is therefore necessary.

---

# ASIC Design Flow

The ASIC flow:

```text
RTL
   ↓
Synthesis
   ↓
Floorplanning
   ↓
Placement
   ↓
Routing
   ↓
Verification
   ↓
GDSII Layout
```

---

# GDSII

GDSII is:

- the final layout format
- used for chip fabrication

It contains the physical representation of the chip layout.

---

## RTL-to-GDSII Flow

The flow acts as:

- a glue framework
- connecting multiple EDA stages together

---

# Key Takeaways

- ASIC design requires RTL, EDA tools, and PDKs.
- Open-source ASIC design became practical after the Sky130 PDK release.
- PDKs act as interfaces between designers and foundries.
- OpenLane automates RTL-to-GDSII flow.
- 130nm technology remains commercially relevant.
- Open-source EDA ecosystems are rapidly growing.