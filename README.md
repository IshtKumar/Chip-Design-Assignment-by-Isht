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
     * Netlist binding and initial place design.
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
     * Lab steps to git clone vsdstdcelldesign
* Inception of Layout CMOS fabrication process.
     * Create Active regions.
     * Formation of N-well and P-well.
     * Formation of gate terminal.
     * Lightly doped drain (LDD) formation.
     * Source A drain formation.
     * Local interconnect formation.
     * Higher level metal formation.
     * Lab introduction to Sky130 basic layers layout and LEF using inverter.
     * Lab steps to create std cell layout and extract spice netlist.
* Sky130 Tech File Labs.
     * Lab steps to create final SPICE deck using Sky130 tech.
     * Lab steps to characterise inverter using Sky130 model files.
     * Lab introduction to Magic tool options and DRC rules.
     * Lab itroduction to Sky130 pdk's and steps to download labs.
     * Lab introduction to Magic and steps to load Sky130 tech-rules.
     * Lab exercise to fix poly.9 error in Sky130 tech-file.
     * Lab exercise to implement poly resistor spacing to diff and tap.
     * Lab challenge exericse to describe DRC error as geometrical construct.
     * Lab challenge to find missing and incorrect rules and fix them.
4. Pre-layout timing analysis and importance of good clock tree.
* Timing modelling using delay tables.
     * Lab steps to convert grid into track info.
     * Lab steps to convert magic layout to std cell LEF.
     * Introduction to timing libs and steps to include new cell in synthesis.
     * Introduction to delay tables.
     * Delay table usage Part 1.
     * Delay table usage Part 2.
     * Lab steps to configure synthesis settings to fix slack and include vsdinv.
* Timing analysis with ideal clocks using openSTA.
     * Setup timing analysis and introduction to flip-flop setup time.
     * Intrduction to clock jitter and uncertainity.
     * Laab steps to configure OpenSTA for post-synth timing analysis.
     * Lab steps to optimize synthesis to reduce setup violations.
     * Lab steps to do basic timing ECO.
* Clock tree synthesis TritonCTS and signal integrity.
     * Clock tree routing and buffering using H-Tree algorithm.
     * Crosstalk and clock net shielding 
     * Lab steps to run CTS using TritonCTS.
     * Lab steps to verify CTS runs.
* Timing analysis with real clocks using openSTA.
     * Setup timing analysis using real clocks
     * Hold timing analysis using real clocks.
     * Lab steps to analyze timing with real clocks using OpenSTA.
     * Lab steps to execute OpenSTA with right timing librariesand CTS assignment.
     * Lab steps to observe impact of bigger CTS buffers on setup and hold timing.
5. Final steps for RTL2GDS using tritonRoute and openSTA.
* Routing and design rule check (DRC).
     * Introduction to Maze Routing A LeeAs algorithm.
     * LeeAs Algorithm conclusion.
     * Design Rule Check.
* Power Distribution Network and routing.
     * Lab steps to build power distribution network.
     * Lab steps from power straps to std cell power.
     * Basis of global and detail routing and configuree TritonRoute.
* TritonRoute Features.
     * TritonRoute featue 1 - Honors pre-processed route guides.
     * TritonRoute Feature 2 & 3 - Inter-guide connectivity and intra-& inter-layer routing.
     * TritonRoute method to handle connectivity.
     * Routing topology algorithm and final files list post-route.
