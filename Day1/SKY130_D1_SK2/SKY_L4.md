# SKY_L4 - Introduction to OpenLANE Detailed ASIC Design Flow

## Introduction

This lecture explains the detailed internal flow of OpenLane ASIC Flow. The lecture discusses:

- synthesis flow
- design exploration
- physical implementation
- testing support
- antenna violation handling
- sign-off and physical verification

The lecture also explains how OpenLane integrates multiple open-source EDA tools together into a complete RTL-to-GDSII framework.

---

# OpenLane ASIC Flow

OpenLane starts with RTL Design and produces final GDSII layout. To function correctly, OpenLane requires:

- Process Design Kit (PDK)
- Standard cell libraries
- Open-source EDA tools

## Open-Source Tools Used in OpenLane

OpenLane integrates several open-source projects such as:

- OpenROAD
- Yosys
- ABC
- Qflow
- Fault
- Magic
- OpenSTA
- TritonRoute

These tools together form the complete ASIC implementation flow.

## RTL Synthesis Flow

The flow starts with RTL Synthesis. The RTL design and constraints are provided to Yosys. Yosys:

- converts RTL into logic circuits
- generates generic gate-level representations
- performs logic transformations

### Technology Mapping using ABC

After generic logic generation ABC maps the logic into standard cells from the library. ABC also performs:

- logic optimization
- area optimization
- timing optimization

### Synthesis Strategies

ABC optimization is controlled using ABC scripts. OpenLane provides multiple predefined synthesis strategies:

- area-optimized strategies
- timing-optimized strategies

Different designs may require different optimization goals.

### Synthesis Exploration Utility

OpenLane includes Synthesis Exploration Utility. This utility:

- compares synthesis strategies
- analyzes delay and area
- helps select optimal configurations

The generated reports show:
- timing results
- area results
- strategy comparisons

## Design Exploration Utility

Another important OpenLane feature is Design Exploration Utility. This utility:

- sweeps multiple design configurations
- evaluates many metrics
- identifies best parameter combinations

### Design Metrics

The exploration report may include:

- timing metrics
- area metrics
- congestion metrics
- violation counts

The lecture mentions:

- more than 35 metrics
- more than 16 configurable parameters


### Purpose of Design Exploration

Design exploration helps:

- determine optimal configurations
- reduce violations
- improve timing
- improve routability

OpenLane already includes pre-explored configurations
for bundled example designs.

### Regression Testing

Design exploration is also used for Continuous Integration (CI). The OpenLane team:

- runs regression testing
- compares results with known-good outputs
- detects unexpected flow changes

## Design for Testability (DFT)

After synthesis optional testing structures can be inserted. This step uses Fault, an open-source DFT tool.

### Functions of Fault Tool

Fault performs:

- scan insertion
- automatic test pattern generation (ATPG)
- pattern compaction
- fault simulation
- fault coverage analysis

### Scan Chains

Additional logic inserted includes scan chains. Scan chains allow:

- post-fabrication testing
- internal state observation
- defect detection

### JTAG Controller

Fault may also insert JTAG controller. This enables:

- external access to scan chains
- testing interface connectivity

## Physical Implementation using OpenROAD

The physical implementation stage is mainly handled by OpenROAD

### Steps Performed by OpenROAD

OpenROAD performs:

- floorplanning
- power planning
- decap insertion
- tap cell insertion
- global placement
- detailed placement
- post-placement optimization
- clock tree synthesis
- global routing

### Detailed Routing

Detailed routing is performed using TritonRoute. Although associated with OpenROAD, TritonRoute operates as a separate routing application.

### Logic Equivalence Checking (LEC)

Physical optimizations may modify the netlist. Therefore LEC is required. This ensures optimized netlist and synthesized netlist remain functionally identical. LEC verifies that:

- optimizations did not alter functionality
- design behavior remains correct

Yosys can be used for equivalence checking.

## Antenna Violations

A special OpenLane step handles Antenna Violations

### What is an Antenna Effect?

Long metal wires may accumulate electrical charge during fabrication. This accumulated charge may damage transistor gates. Thus wire lengths must be controlled.

### Solutions for Antenna Violations

Two major solutions:

- Metal Bridging
    - Routing temporarily moves to upper metal layers then returns back. 
    - This reduces effective antenna impact.
- Antenna Diodes
    - Special diodes are inserted near vulnerable transistor gates.
    - These diodes leak away accumulated charge

### OpenLane Preventive Approach

OpenLane introduces fake antenna diodes. After placement, fake diode cells are inserted near inputs. After routing antenna checks are performed, if violations exist, fake diodes are replaced by real antenna diodes.

### OpenROAD Antenna Handling

Recent OpenROAD updates include:

- automatic antenna diode insertion
- ARC tool for antenna checking

OpenLane allows users to choose between:

- OpenLane approach
- OpenROAD approach

## Sign-Off Flow

After routing Sign-Off and physical verification is performed. Major sign-off steps include:

- Static Timing Analysis (STA)
- Design Rule Check (DRC)
- Layout Versus Schematic (LVS)

### Timing Sign-Off

Timing sign-off includes RC extraction followed by static timing analysis, performed using OpenSTA. Reports generated include:

- setup violations
- hold violations
- timing summaries

### Design Rule Check (DRC)

DRC is performed using Magic. Magic verifies:

- spacing rules
- width rules
- enclosure rules
- fabrication compliance

### Layout Versus Schematic (LVS)

LVS verifies layout connectivity matches schematic/netlist connectivity. The flow uses:

- Magic for extraction
- Netgen for comparison

## Final Goal of OpenLane

The overall objective is automated clean GDSII generation with

- no DRC violations
- no LVS violations
- minimal timing violations

# Complete OpenLane Flow

```text
RTL
 ↓
Yosys Synthesis
 ↓
ABC Optimization & Mapping
 ↓
DFT Insertion (Optional)
 ↓
Floorplanning
 ↓
Placement
 ↓
Clock Tree Synthesis
 ↓
Routing
 ↓
Antenna Fixing
 ↓
STA / DRC / LVS
 ↓
Final GDSII
```

---

# Key Takeaways

- OpenLane integrates multiple open-source EDA tools.
- Yosys performs RTL synthesis.
- ABC handles optimization and technology mapping.
- OpenROAD manages physical implementation.
- Fault enables scan insertion and testing support.
- Antenna violations must be handled carefully.
- Magic and Netgen perform physical verification.
- OpenSTA handles timing verification.
- OpenLane aims for fully automated clean layout generation.