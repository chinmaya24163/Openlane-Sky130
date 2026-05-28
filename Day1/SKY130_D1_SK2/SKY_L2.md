# SKY_L2 - Simplified RTL2GDS Flow

## Introduction

This lecture introduces the complete RTL-to-GDSII ASIC Design Flow. The lecture explains the major stages involved in converting RTL design into fabrication-ready chip layout. The major implementation steps discussed are:

- Synthesis
- Floorplanning
- Placement
- Clock Tree Synthesis (CTS)
- Routing
- Physical Verification and Sign-off

---

# ASIC Design Flow Overview

The ASIC flow starts with RTL Model and ends with GDSII Layout, which is the final layout format used for fabrication. The process of producing the final layout is commonly called Tape-out. It is called tapeout because, historically, the finalized blueprints (mask files) were physically written onto heavy reels of magnetic tape to be shipped to the manufacturing facility (or foundry).

---

# Major Stages in ASIC Flow

```text
RTL
 ↓
Synthesis
 ↓
Floorplanning
 ↓
Placement
 ↓
Clock Tree Synthesis
 ↓
Routing
 ↓
Sign-off
 ↓
GDSII Layout
```

---

## 1. Synthesis

### Purpose

Synthesis converts RTL code into gate-level circuits using standard cells from the standard cell library. The synthesis output is:

### Gate-Level Netlist

The netlist:

- contains interconnected logic gates
- is functionally equivalent to the RTL

The netlist is generally represented using HDL.

### Standard Cells

Standard cells are:

- predefined logic building blocks
- obtained from standard cell libraries

Examples:
- AND gates
- OR gates
- Flip-flops
- Buffers
- Multiplexers

Each standard cell:

- has fixed height
- has variable width
- is aligned to placement rows

The width is usually an integer multiple of site width. Each standard cell contains multiple representations called views. Different EDA tools use different views. Examples: 

- Liberty View (.lib)

    - Contains:

        - timing models
        - delay information
        - power models

    - Used for:

        - timing analysis
        - synthesis

- HDL Behavioral View

    - Contains behavioral HDL description of the cell
    - Used for simulation

- SPICE/CDL View

    - Contains transistor-level circuit description
    - Used for circuit simulation and analog verification

- Layout Views

    - Two layout representations are mentioned:
        - GDSII View: detailed physical layout
        - LEF View: abstract physical representation

    - Used during:
        - placement
        - routing

---

## 2. Floorplanning and Power Planning

The meaning of floorplanning depends on whether a macro is being designed or the complete chip is being designed.

### Objectives of Floorplanning

Floorplanning aims to:

- organize silicon area
- define component locations
- prepare routing resources

---

### Chip Floorplanning

In chip-level floorplanning:

- die area is partitioned
- macro locations are determined
- chip components are arranged

---

### Macro Floorplanning

In macro floorplanning:

- macro dimensions are defined
- pin locations are fixed

### Rows and Routing Tracks

During floorplanning:

- placement rows are defined
- routing tracks are defined

These are later used during:

- placement
- routing

### Power Planning

Power planning constructs the Power Distribution Network (PDN). The PDN distributes:

- VDD
- Ground

throughout the chip.

### Power Distribution Structures

Power is distributed using:

- power rings
- vertical metal straps
- horizontal metal straps

These structures reduce:

- IR drop
- resistance
- electromigration effects

### Upper Metal Layers for Power

Upper metal layers are preferred because:

- they are thicker
- they have lower resistance

This improves power integrity.

## 3. Placement

Placement arranges:

- standard cells
- macros

onto predefined rows.

### Placement Objective

Connected cells should be placed close together. This helps reduce:

- interconnect delay
- routing congestion

### Placement Stages

Placement generally occurs in two stages:

- Global placement
    - finds approximate optimal locations
    - does not guarantee legal placement
    - Cells may:
        - overlap
        - go outside rows
- Detailed Placement
    - legalizes placement
    - removes overlaps
    - aligns cells properly while minimally disturbing global placement results.

## 4. Clock Tree Synthesis (CTS)

Before signal routing clock routing must be completed. CTS creates Clock Distribution Network.

### Clock Tree Structure

The clock network resembles a tree structure, where:

- clock source = root
- clock sinks = leaves

Clock sinks include:

- flip-flops
- sequential elements

### CTS Objectives

CTS aims to minimize:

- clock skew
- clock latency

while maintaining:

- proper clock shape
- timing quality

### Clock Skew

Clock skew refers to difference in clock arrival times at different sequential elements.

### Clock Tree Structures

Common CTS structures:

- H-tree
- X-tree
- Wishbone
- Hybrid structures

## 5. Routing

After CTS, signal routing is performed. Routing connects:

- placed cells
- nets
- pins

using metal layers

### Metal Layer Information

The PDK defines:

- metal thickness
- routing pitch
- routing tracks
- minimum widths
- via definitions


### Sky130 Routing Layers

Sky130 defines 6 Routing Layers:

- Local Interconnect Layer: Titanium Nitride layer
- Upper 5 Layers: Aluminum routing layers

### Global Routing vs Detailed Routing

Routing is generally divided into:

- Global Routing
    - Uses coarse routing grids
    - Generates routing guides
- Detailed Routing
    - fine-grained routing grids
    - Implements actual wire geometries

## 6. Physical Verification And Sign-off

After routing final layout verification is performed.

### Design Rule Check (DRC)

DRC ensures layout follows all fabrication rules. Examples:

- spacing rules
- width rules
- enclosure rules

### Layout Versus Schematic (LVS)

LVS checks whether final layout matches gate-level netlist. It ensures logical correctness.

### Static Timing Analysis (STA)

STA verifies:

- timing constraints
- setup timing
- hold timing
- operating frequency

without requiring simulation vectors.

## Final Outcome

After successful verification:

- final GDSII layout is generated
- design becomes fabrication-ready

---

# Key Takeaways

- ASIC flow converts RTL into fabrication-ready layout.
- Synthesis generates gate-level netlist.
- Standard cells contain multiple views for EDA tools.
- Floorplanning organizes chip area and power network.
- Placement arranges cells optimally.
- CTS distributes clock signals with minimal skew.
- Routing connects all signals using metal layers.
- DRC, LVS, and STA ensure design correctness.
- GDSII is the final layout format used for fabrication.