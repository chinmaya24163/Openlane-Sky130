# Openlane Sky130 Workshop

Documentation and notes for the Openlane Sky130 Physical Design Workshop.

---

# Day 1 - Inception of Open Source EDA

## SKY130_D1_SK1 - How to talk to computers

- [SKY_L1 - Introduction to QFN-48 Package](Day1/SKY130_D1_SK1/SKY_L1.md)
- [SKY_L2 - Introduction to RISC-V](Day1/SKY130_D1_SK1/SKY_L2.md)
- [SKY_L3 - From Software Applications to Hardware](Day1/SKY130_D1_SK1/SKY_L3.md)

## SKY130_D1_SK2 - SoC design and OpenLANE

- [SKY_L1 - Introduction to all components of open-source digital ASIC design](Day1/SKY130_D1_SK2/SKY_L1.md)
- [SKY_L2 - Simplified RTL2GDS flow](Day1/SKY130_D1_SK2/SKY_L2.md)
- [SKY_L3 - Introduction to OpenLANE](Day1/SKY130_D1_SK2/SKY_L3.md)
- [SKY_L4 - Introduction to OpenLANE detailed ASIC design flow](Day1/SKY130_D1_SK2/SKY_L4.md)

## SKY130_D1_SK3 - Get familiar to open-source EDA tools

- [SKY_L1 - OpenLANE Directory Structure](Day1/SKY130_D1_SK3/SKY_L1.md)
- [SKY_L2 - Design Preparation Step](Day1/SKY130_D1_SK3/SKY_L2.md)
- [SKY_L3 - Review files after design prep and run synthesis](Day1/SKY130_D1_SK3/SKY_L3.md)
- [SKY_L4 - OpenLANE Project Git Link Description](Day1/SKY130_D1_SK3/SKY_L4.md)
- [SKY_L5 - Steps to characterize synthesis results](Day1/SKY130_D1_SK3/SKY_L5.md)

---

# Day 2 - Good Floorplan vs Bad Floorplan

## SKY130_D2_SK1 - Chip Floor planning considerations

- [SKY_L1 - Utilization factor and aspect ratio](Day2/SKY130_D2_SK1/SKY_L1.md)
- [SKY_L2 - Concept of pre-placed cells](Day2/SKY130_D2_SK1/SKY_L2.md)
- [SKY_L3 - Decoupling capacitors and power planning](Day2/SKY130_D2_SK1/SKY_L3.md)
- [SKY_L4 - Power planning](Day2/SKY130_D2_SK1/SKY_L4.md)
- [SKY_L5 - Pin placement and logical cell placement blockage](Day2/SKY130_D2_SK1/SKY_L5.md)
- [SKY_L6 - Steps to run floorplan using OpenLANE](Day2/SKY130_D2_SK1/SKY_L6.md)
- [SKY_L7 - Review floorplan files and steps to view floorplan](Day2/SKY130_D2_SK1/SKY_L7.md)
- [SKY_L8 - Review floorplan layout in Magic](Day2/SKY130_D2_SK1/SKY_L8.md)

## SKY130_D2_SK2 - Library Binding and Placement

* [SKY_L1 - Netlist binding and initial place design](Day2/SKY130_D2_SK2/SKY_L1.md)
* [SKY_L2 - Optimize placement using estimated wire-length and capacitance](Day2/SKY130_D2_SK2/SKY_L2.md)
* [SKY_L3 - Final placement optimization](Day2/SKY130_D2_SK2/SKY_L3.md)
* [SKY_L4 - Need for libraries and characterization](Day2/SKY130_D2_SK2/SKY_L4.md)
* [SKY_L5 - Congestion aware placement using RePlAce](Day2/SKY130_D2_SK2/SKY_L5.md)

## SKY130_D2_SK3 - Cell design and characterization flows

* [SKY_L1 - Inputs for cell design flow](Day2/SKY130_D2_SK3/SKY_L1.md)
* [SKY_L2 - Circuit design steps](Day2/SKY130_D2_SK3/SKY_L2.md)
* [SKY_L3 - Layout design steps](Day2/SKY130_D2_SK3/SKY_L3.md)
* [SKY_L4 - Typical characterization flow](Day2/SKY130_D2_SK3/SKY_L4.md)

## SKY130_D2_SK4 - General timing characterization parameters

* [SKY_L1 - Timing threshold definitions](Day2/SKY130_D2_SK4/SKY_L1.md)
* [SKY_L2 - Propagation delay and transition time](Day2/SKY130_D2_SK4/SKY_L2.md)

---

# Day 3 - Design Library Cell using Magic Layout and ngspice Characterization

## SKY130_D3_SK1 - Labs for CMOS inverter ngspice simulations

* [SKY_L0 - IO placer revision](Day3/SKY130_D3_SK1/SKY_L0.md)
* [SKY_L1 - SPICE deck creation for CMOS inverter](Day3/SKY130_D3_SK1/SKY_L1.md)
* [SKY_L2 - SPICE simulation lab for CMOS inverter](Day3/SKY130_D3_SK1/SKY_L2.md)
* [SKY_L3 - Switching Threshold Vm](Day3/SKY130_D3_SK1/SKY_L3.md)
* [SKY_L4 - Static and dynamic simulation characteristics](Day3/SKY130_D3_SK1/SKY_L4.md)
* [SKY_L5 - Lab steps to git clone vsdstdcelldesign](Day3/SKY130_D3_SK1/SKY_L5.md)

## SKY130_D3_SK2 - Inception of Layout and CMOS Fabrication Process

* [SKY_L1 - Create Active Regions](Day3/SKY130_D3_SK2/SKY_L1.md)
* [SKY_L2 - Formation of N-well and P-well](Day3/SKY130_D3_SK2/SKY_L2.md)
* [SKY_L3 - Formation of gate terminal](Day3/SKY130_D3_SK2/SKY_L3.md)
* [SKY_L4 - Lightly doped drain formation](Day3/SKY130_D3_SK2/SKY_L4.md)
* [SKY_L5 - Source-drain formation](Day3/SKY130_D3_SK2/SKY_L5.md)
* [SKY_L6 - Local interconnect formation](Day3/SKY130_D3_SK2/SKY_L6.md)
* [SKY_L7 - Higher level metal formation](Day3/SKY130_D3_SK2/SKY_L7.md)
* [SKY_L8 - Lab introduction to inverter layout using Magic](Day3/SKY130_D3_SK2/SKY_L8.md)
* [SKY_L9 - Lab steps to create inverter layout in Magic](Day3/SKY130_D3_SK2/SKY_L9.md)

## SKY130_D3_SK3 - Sky130 Tech File Labs

* [SKY_L1 - Lab steps to create final layout in Magic](Day3/SKY130_D3_SK3/SKY_L1.md)
* [SKY_L2 - Lab steps to characterize inverter using Magic](Day3/SKY130_D3_SK3/SKY_L2.md)
* [SKY_L3 - Lab introduction to Sky130 tech file](Day3/SKY130_D3_SK3/SKY_L3.md)
* [SKY_L4 - Lab introduction to DRC rules](Day3/SKY130_D3_SK3/SKY_L4.md)
* [SKY_L5 - Lab introduction to Magic and DRC tests](Day3/SKY130_D3_SK3/SKY_L5.md)
* [SKY_L6 - Lab exercise to fix poly.9 error](Day3/SKY130_D3_SK3/SKY_L6.md)
* [SKY_L7 - Lab exercise to implement poly resistor spacing rule](Day3/SKY130_D3_SK3/SKY_L7.md)
* [SKY_L8 - Lab challenge exercise for DRC correction](Day3/SKY130_D3_SK3/SKY_L8.md)
* [SKY_L9 - Lab challenge to find missing DRC rules](Day3/SKY130_D3_SK3/SKY_L9.md)

---

# Day 4 - Pre-layout Timing Analysis and Importance of Good Clock Tree

## SKY130_D4_SK1 - Timing Modelling using Delay Tables

* [SKY_L1 - Lab steps to convert grid info to track info](Day4/SKY130_D4_SK1/SKY_L1.md)
* [SKY_L2 - Lab steps to convert Magic layout to std cell LEF](Day4/SKY130_D4_SK1/SKY_L2.md)
* [SKY_L3 - Introduction to timing libs and characterization](Day4/SKY130_D4_SK1/SKY_L3.md)
* [SKY_L4 - Introduction to delay tables](Day4/SKY130_D4_SK1/SKY_L4.md)
* [SKY_L5 - Delay table usage Part 1](Day4/SKY130_D4_SK1/SKY_L5.md)
* [SKY_L6 - Delay table usage Part 2](Day4/SKY130_D4_SK1/SKY_L6.md)
* [SKY_L7 - Lab steps to configure synthesis settings](Day4/SKY130_D4_SK1/SKY_L7.md)

## SKY130_D4_SK2 - Timing Analysis with Ideal Clocks using OpenSTA

* [SKY_L1 - Setup timing analysis using OpenSTA](Day4/SKY130_D4_SK2/SKY_L1.md)
* [SKY_L2 - Introduction to clock jitter and uncertainty](Day4/SKY130_D4_SK2/SKY_L2.md)
* [SKY_L3 - Lab steps to configure OpenSTA](Day4/SKY130_D4_SK2/SKY_L3.md)
* [SKY_L4 - Lab steps to optimize timing](Day4/SKY130_D4_SK2/SKY_L4.md)
* [SKY_L5 - Lab steps to do basic timing ECO](Day4/SKY130_D4_SK2/SKY_L5.md)

## SKY130_D4_SK3 - Clock Tree Synthesis TritonCTS and Signal Integrity

* [SKY_L1 - Clock tree routing and buffering](Day4/SKY130_D4_SK3/SKY_L1.md)
* [SKY_L2 - Crosstalk and clock net shielding](Day4/SKY130_D4_SK3/SKY_L2.md)
* [SKY_L3 - Lab steps to run CTS using TritonCTS](Day4/SKY130_D4_SK3/SKY_L3.md)
* [SKY_L4 - Lab steps to verify CTS quality](Day4/SKY130_D4_SK3/SKY_L4.md)

## SKY130_D4_SK4 - Timing Analysis with Real Clocks using OpenSTA

* [SKY_L1 - Setup timing analysis using real clocks](Day4/SKY130_D4_SK4/SKY_L1.md)
* [SKY_L2 - Hold timing analysis using real clocks](Day4/SKY130_D4_SK4/SKY_L2.md)
* [SKY_L3 - Lab steps to analyze timing after CTS](Day4/SKY130_D4_SK4/SKY_L3.md)
* [SKY_L4 - Lab steps to execute timing ECO](Day4/SKY130_D4_SK4/SKY_L4.md)
* [SKY_L5 - Lab steps to observe improvements after ECO](Day4/SKY130_D4_SK4/SKY_L5.md)

---

# Day 5 - Final Steps for RTL2GDS using TritonRoute and OpenSTA

## SKY130_D5_SK1 - Routing and Design Rule Check (DRC)

* [SKY_L1 - Introduction to Maze Routing](Day5/SKY130_D5_SK1/SKY_L1.md)
* [SKY_L2 - Lee's Algorithm Concepts](Day5/SKY130_D5_SK1/SKY_L2.md)
* [SKY_L3 - Design Rule Check](Day5/SKY130_D5_SK1/SKY_L3.md)

## SKY130_D5_SK2 - Power Distribution Network and Routing

* [SKY_L1 - Lab steps to build power distribution network](Day5/SKY130_D5_SK2/SKY_L1.md)
* [SKY_L2 - Lab steps from power planning to routing](Day5/SKY130_D5_SK2/SKY_L2.md)
* [SKY_L3 - Basics of global and detailed routing](Day5/SKY130_D5_SK2/SKY_L3.md)

## SKY130_D5_SK3 - TritonRoute Features and Final Routing

* [SKY_L1 - TritonRoute feature overview](Day5/SKY130_D5_SK3/SKY_L1.md)
* [SKY_L2 - TritonRoute Features and Algorithms](Day5/SKY130_D5_SK3/SKY_L2.md)
* [SKY_L3 - TritonRoute methodology](Day5/SKY130_D5_SK3/SKY_L3.md)
* [SKY_L4 - Routing topology algorithms](Day5/SKY130_D5_SK3/SKY_L4.md)

---

# Github Repo Link

---