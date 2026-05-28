# SKY_L3 - Introduction to OpenLANE

## Introduction

This lecture introduces:

- OpenLane
- motivation behind its development
- goals of the project
- supported technologies
- operation modes
- STRIVE SoC family

The lecture explains how OpenLane attempts to provide a fully automated open-source RTL-to-GDSII ASIC implementation flow.

---

# Challenges with Open-Source EDA Flows

Building a digital ASIC flow is relatively manageable when:

- commercial EDA tools are available
- designers have strong expertise

However, building a fully open-source ASIC flow is significantly more difficult.

Several issues must be addressed:

- tool qualification
- tool calibration
- missing tools
- interoperability between tools
- automation challenges

This motivated the creation of OpenLane.

---

# OpenLane

OpenLane is an open-source ASIC implementation flow.It was developed by eFabless, released under Apache License 2.0, and hosted publicly on GitHub.

## Goals of OpenLane

The primary goal of OpenLane is fully automated ASIC implementation with:

- no human intervention
- clean GDSII generation
- complete RTL-to-GDSII automation

### Meaning of "Clean GDSII"

A clean GDSII means:

- no DRC violations
- no LVS violations
- no timing violations

## Initial Motivation Behind OpenLane

OpenLane originally started as a flow for STRIVE open-source SoC experiments. The aim was to build:

- open RTL
- open EDA flow
- open PDK
- open SoCs

## STRIVE SoC Family

The lecture introduces multiple members of the STRIVE family.

### STRIVE 1

Features:

- implemented using Sky130 high-density standard cell library
- contains 1 KB SRAM

### STRIVE 2

Similar to STRIVE 1 except SRAM is generated using OpenRAM compiler.

### STRIVE 2A

Similar to STRIVE 2 but with its hierarchy modified.
Purpose - achieve 100% RTL-to-GDSII automation

### STRIVE 3

Similar to STRIVE 1 but uses a different standard cell library

### STRIVE 5

Features:

- 8 SRAM banks
- each bank = 1 KB
- total SRAM = 8 KB
- SRAM is generated using OpenRAM compiler.

### STRIVE 6

Similar to STRIVE 2 but includes Design for Testability (DFT) structures.

## OpenLane Technology Support

OpenLane is primarily tuned for SkyWater Sky130 PDK. It has also been tested with:

- XFAB 180nm
- GlobalFoundries 130G

## Containerized Flow

OpenLane is Containerized.
Meaning:

- works out of the box
- dependencies are preconfigured
- setup complexity is reduced

This simplifies:
- installation
- portability
- reproducibility

## OpenLane Usage Modes

OpenLane supports two modes of operation:

### 1. Autonomous Mode

Also called Push-Button Flow. In this mode:

- configurations are provided
- flow executes automatically
- final GDSII and reports are generated

This mode is ideal for complete automated runs.

### 2. Interactive Mode

In interactive mode:

- commands are executed step-by-step
- intermediate results can be inspected
- experimentation becomes easier

Useful for:

- debugging
- learning
- design optimization

## Macro and Chip Hardening

OpenLane can be used for Macro Hardening or Full Chip Hardening. Hardening means converting RTL into fabrication-ready GDSII layout.

## Design Space Exploration (DSE)

ASIC flows contain many:

- tunable parameters
- configuration variables

The optimal settings depend on:

- design characteristics
- designer expertise

### Purpose of Design Space Exploration

DSE helps:

- sweep multiple configurations
- compare results
- automatically determine optimal settings

This improves:

- timing
- area
- power
- routability

## Incremental Development

The OpenLane ecosystem continues evolving with:

- more designs
- improved automation
- better timing handling
- expanded support

## Overall OpenLane Vision

OpenLane aims to democratize ASIC design by enabling:

- open hardware
- open PDKs
- open RTL
- open EDA flows

allowing students, researchers, and developers to build fabrication-ready ASICs.

---

# Key Takeaways

- OpenLane is an open-source RTL-to-GDSII ASIC flow.
- It was developed by eFabless.
- The flow aims for fully automated clean GDSII generation.
- OpenLane supports both macro and full-chip hardening.
- Autonomous and interactive operation modes are available.
- Design Space Exploration helps optimize flow parameters.
- OpenLane is primarily tuned for Sky130 technology.
- STRIVE SoC family served as the original OpenLane use case.