# Chip-Design-Assignment-by-Isht
## Advanced Physical Design Using OpenLane/Sky130

##### Author :- Isht Kumar

This is the compilation of notes provided by Kunal sir and his team for the Advanced Level of the Chip Design Course, Advanced Physical Design using Sky130 and OpenLANE.

## Table of Content
1. Inception of open-source EDA, OpenLANE and Sky130PDK
* How to talk to Computers.
     * Introduction to QFN-48 Package, chip, pads, core, die and IPs.
     * Introduction to RISC-V.
     * From Software Applications to Hardware.
* SoC design and OpenLANE.
     * Introduction to all components of open-source digital asic design.
     * Simplified RTL2GDS flow.
     * Introduction to OpenLANE and Strive chipsets.
     * Introduction to OpenLANE detailed ASIC design flow.
* Get familiar to open-source EDA tools.
     * OpenLANE Directory structure in detail.
     * Design preparation step.
     * Review files after design prep. and run synthesis.
     * OpenLANE Project Git Link Description.
     * Steps to characterize synthesis results.
2. Good foorplan vs bad floorplan and introduction to library cells.
* Chip Floor planning considerations.
     * Utilisation factor and aspect ratio.
     * Concept of pre-placed cells.
     * De-coupling capacitors.
     * Power planning.
     * Pin placement and logical cell placement blockage.
     * Steps to run floorplan using OpenLANE.
     * Revieew floorplan files and steps to view floorplan.
     * Reviw floorplan layout in Magic.
* Library Binding and Placement.
     * Netlist bindig and initial place design.
     * Optimize placement using estimated wire-length and capacitance.
     * Final placement optimization.
     * Need for libraries and characterisation.
     * Congestion aware placement using PePlAce.
* Cell design and characterisation flows.
     * Inputs for cell design flow.
     * Circuit design step.
     * Layout design step.
     * Typical characterisation flow.
* General timing characterization parameters.
     * Timing thresholds definitions.
     * Propogation delay and transition time.
3. Design library cell using Magic Layout and ngspice characterisation.
* Labs for CMOS inverter ngspice simulations.
     * IO placer revision.
     * SPICE deck creation for CMOS inverter.
     * SPICE simulation lab for CMOS inverter.
     * Switching Threshold Vm.
     * Static and dynamic simulation of CMOS inverter.
