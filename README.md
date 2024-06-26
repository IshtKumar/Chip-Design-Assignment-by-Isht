# Chip-Design-Assignment-by-Isht
## Advanced Physical Design Using OpenLane/Sky130

##### Author :- Isht Kumar

#### This is the compilation of notes provided by Kunal sir, his team, the IIIT Bangalore team and Sudarshan sir for the Advanced Level of the Chip Design Course, Advanced Physical Design using Sky130 and OpenLANE. All the information and the images are provided by Kunal sir and the VSD team, Sudarshan sir and IIIT Bangalore team. I thank all of them for the mentoring precious knowledge they provided through online sessions, seminars, and videos.

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
     * Lab steps to execute OpenSTA with right timing libraries and CTS assignment.
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

## Inception of open-source EDA, OpenLANE and Sky130PDK


## How to talk to computers.


### Introduction to QFN-48 Package, chip, pads, core, die and IPs.
Arduino is an open-source electronics platform based on easy-to-use hardware and software which is taken as an example here.
<img src="https://private-user-images.githubusercontent.com/163589731/313405849-7c190d7b-f48b-43a5-8697-a2271a28e9aa.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTEyNzczMzIsIm5iZiI6MTcxMTI3NzAzMiwicGF0aCI6Ii8xNjM1ODk3MzEvMzEzNDA1ODQ5LTdjMTkwZDdiLWY0OGItNDNhNS04Njk3LWEyMjcxYTI4ZTlhYS5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMzI0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDMyNFQxMDQzNTJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01ZDY1YzcxNjRjODE5OGM4YWY1MTdiZDM3MWI4NmM2MjJlMDI2NjA1YTkxNGRlMzUyYjA2ZWYxM2YyMzFlYzE2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.W6HB2uD0Ume3Vz1m5Dfl4sjUI8e5Yn9zUTAxdhkN_pY">

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)



The above image is an Arduino Leonardo microcontroller board based on the ATmega32u4. It has 20 digital input/output pins (of which 7 can be used as PWM outputs and 12 as analog inputs), a 16 MHz crystal oscillator, a micro USB connection, a power jack, an ICSP header, and a reset button.These boards operate at 5 volts. The yellow circled part ( the processor) is what we will be discussing about.



The below image describes about the processor/SoC or system-on a-chip (which we had seen in the above picture). 

<img src="https://private-user-images.githubusercontent.com/163589731/313406180-c3176cb9-34db-4581-a858-aeab397be237.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTEyNzczMzIsIm5iZiI6MTcxMTI3NzAzMiwicGF0aCI6Ii8xNjM1ODk3MzEvMzEzNDA2MTgwLWMzMTc2Y2I5LTM0ZGItNDU4MS1hODU4LWFlYWIzOTdiZTIzNy5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMzI0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDMyNFQxMDQzNTJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iNTM2ZDNlMTI1NmQ5Nzc1NmM3ZDc4ZTBlMTQ0Yjc4MDU2MGRmYzU1ODQ2YjJjYzRiOGRhZTQ3ZjQ1ZjQ5ZjVmJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.Jy-Kwjjrk6gq-GkyeHzokbDgLj9OM_TYcno9xPgtHo0">

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)






The below picture is called as an integrated circuit package (named the 'QFN-48 package') and inside it is the chip. A package is a metal, plastic, glass, or ceramic casing containing one or more discrete semiconductor devices or integrated circuits. The package provides the mechanical and electrical interface between the chip and the printed board, as well as protecting the chip and helping heat dissipation.


![Arduino Leonardo Package](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/c4563165-ba06-4aa2-9de8-2f20f0d290b3)

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)


The abbreviation QFN stands for quad flat no-lead package. A QFN-48 package is a particular type of Integrated Circuit pakage with 48 electrical connections.


![Package](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/798b38d6-07b1-40ff-95e6-2fff9ec8dda5)

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)


This is the chip located inside the package connected to the outside material through the pads.


![Components](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/54f13488-a99c-49bf-a1c3-345aef675f34)

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)


### Components :-


#### Pads - Pad consists of a square of top-level metal on a side that is either soldered to bond wire connecting to a package or coated with lead solder ball. Pad refers to metal square only or to the complete I/O cell containing the metal, ESD protection circuit, and I/O transistors. The function of a pad is an electrial terminal used to connect externally to the IC.

#### Core - A core is the section of a chip where the fundamental logic of the design is placed. 

#### Die - A die, in the context of processors, refers to a small piece of sillicon material on which the microprocessor is fabricated. It serves as the foundation for building the central processing unit (CPU) that powers computers and other electronic devices.


### Other Components (which are not mentioned) :-


#### Macros - Macros is an essential component in the VLSI design cycle before the final packaged chip is ready to use. Macro cells are the memory cells, intellectual property which an analog design team has designed.

#### Foundry IPs - IP (Intellectual Property), refers to a reusable unit of logic or circuitry that performs a specific function and can be integrated into a larger design. IPs are pre-validated, making them a time saving saolution for VLSI design.



### Introduction to RISC-V.



#### What is RISC-V ?


RISC-V (pronounced "risk-five") is an open standard instruction set architecture (ISA) based on established reduced instruction set computer (RISC) principles.


![Screenshot 2024-03-26 211744](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/4fcef972-2c3c-4110-a966-d657b98f7646)

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)



### From Software Applications to Hardware.


![Software to Hardware](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/3830fbce-73cf-42bc-942f-de2bbe869271)

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)



The above image shows the software application is processed within system software, where it undergoes conversion into binary language. System software consists of the operating system (OS), compiler, and assembler. The operating system manages memory, handles I/O operations, and allocates resources. Subsequently, the operating system produces small functions in languages such as C/C++/Java, which are then compiled into executable files (.exe) by the corresponding compiler. The syntax of these instructions depends on the available hardware architecture, such as Intel, ARM, MIPS, or RISC-V. The assembler's role is to translate these instructions into binary code comprehensible by the machine. These binary instructions are then transmitted to the hardware, where they are interpreted, and the desired outputs are generated according to the underlying logic.

The below image shows the stopwatch app turning into a hardware.

![Screenshot 2024-03-27 101326](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/be969a90-c796-4101-8977-7d8200bd3f07)

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)



The below image shows the process : ISA -> HDL -> Netlist -> Physical Design

![Screenshot 2024-03-27 102545](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/f0752880-91cd-4a30-b17f-ae60b3c11639)

#### (Source - Videos provided from the VSD platform made accessible to me by Kunal sir and the sessions conducted by Sudarshan Sir.)



## SoC design and OpenLANE.

### Introduction to all components of open-source digital asic design. 


We can design an ASIC using : RTL Designs
                              EDA Tools
                              PDK Data


![ASIC Design](https://github.com/IshtKumar/Chip-Design-Assignment-by-Isht/assets/164362610/734dde8f-121b-4a48-a4f2-53701c419c9c)


