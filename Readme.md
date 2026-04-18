
# PicoRV32A SoC Design and Planning

## 📑 Index

- [Section 1: OpenLANE Flow & Synthesis](#section-1-openlane-flow--synthesis)
  - [Run OpenLANE in Interactive Mode](#run-openlane-in-interactive-mode)
  - [Design Preparation (prep)](#design-preparation-prep)
  - [Run Synthesis](#run-synthesis)
  - [Synthesis Report Analysis](#synthesis-report-analysis)
  - [Flop Ratio Calculation](#flop-ratio-calculation)

- [Section 2: Floorplanning](#floorplanning)
  - [Run Floorplan](#run-floorplan)
  - [Floorplan DEF Analysis](#floorplan-def-analysis)
  - [Die Area Calculation](#die-area-calculation)
  - [Load Floorplan in Magic](#load-floorplan-in-magic)

- [Section 3: Standard Cell Design (Inverter)](#section-3-standard-cell-design-inverter)
  - [Clone Standard Cell Repository](#clone-standard-cell-repository)
  - [Open Layout in Magic](#open-layout-in-magic)
  - [Layout Exploration](#layout-exploration)
  - [DRC Error Demonstration](#drc-error-demonstration)
  - [Spice Extraction](#spice-extraction)
  - [Generated SPICE File](#generated-spice-file)
  - [SPICE File Editing](#spice-file-editing)
  - [NGSpice Simulation Run](#ngspice-simulation-run)
  - [Output Waveform](#output-waveform)
  - [Rise/Fall Time Calculation](#risefall-time-calculation)
  - [Cell Delay Calculation](#cell-delay-calculation)

- [Section 4: Integration & Timing Analysis](#section-4-integration--timing-analysis)
  - [Track Grid Alignment Check](#track-grid-alignment-check)
  - [Generate LEF](#generate-lef)
  - [Modify config.tcl](#modify-configtcl)
  - [Re-run Synthesis with Custom Cell](#re-run-synthesis-with-custom-cell)
  - [Run Floorplan + Placement](#run-floorplan--placement)
  - [Pre-STA Setup](#pre-sta-setup)
  - [Run STA (OpenSTA)](#run-sta-opensta)
  - [Timing Optimization](#timing-optimization)
  - [Run CTS](#run-cts)
  - [PDN Generation](#pdn-generation)

- [Routing](#routing)
  - [Run Routing](#run-routing)
  - [Routed Layout](#routed-layout)

- [Post-Route Analysis](#post-route-analysis)
  - [SPEF Extraction](#spef-extraction)
  - [Post-Route STA](#post-route-sta)
  - [Final Timing Report](#final-timing-report)

---

## Section 1: OpenLANE Flow & Synthesis
Overview of synthesis flow using OpenLANE.

### Run OpenLANE in Interactive Mode
Invoking OpenLANE Docker and interactive shell.

![image](./images/s1_1.png)

---

### Design Preparation (prep)
Preparing design environment and variables.

![image](./images/s1_2.png)

---

### Run Synthesis
Converting RTL to gate-level netlist.

![image](./images/s1_3.png)

---

### Synthesis Report Analysis
Reviewing synthesis statistics and utilization.

![image](./images/s1_4.png)

---

### Flop Ratio Calculation
Calculating DFF percentage in design.

![image](./images/s1_5.png)

---

## Section 2: Floorplanning
Defining chip layout and dimensions.

### Run Floorplan
Generating initial floorplan.

![image](./images/s1_6.png)

---

### Floorplan DEF Analysis
Extracting layout dimensions.

![image](./images/s1_7.png)

---

### Die Area Calculation
Computing total chip area.

![image](./images/s1_8.png)

---

### Load Floorplan in Magic
Viewing layout in Magic.

![image](./images/s1_9.png)

---

## Section 3: Standard Cell Design (Inverter)
Custom cell design and validation.

### Clone Standard Cell Repository
Downloading inverter layout files.

![image](./images/s3_1.png)

---

### Open Layout in Magic
Loading inverter layout.

![image](./images/s3_2.png)

---

### Layout Exploration
Understanding transistor connections.

![image](./images/s3_3.png)

---

### DRC Error Demonstration
Observing rule violations.

![image](./images/s3_4_2.png)
![image](./images/s3_4_3.png)
![image](./images/s3_4_4.png)
![image](./images/s3_4_5.png)
![image](./images/s3_4_6.png)
![image](./images/s3_4_7.png)
![image](./images/s3_4_8.png)

---

### Spice Extraction
Generating SPICE netlist.

![image](./images/s3_5_1.png)
![image](./images/s3_5_2.png)

---

### Generated SPICE File
Viewing extracted netlist.

![image](./images/s3_6.png)

---

### SPICE File Editing
Preparing for simulation.

![image](./images/s3_7.png)

---

### NGSpice Simulation Run
Running circuit simulation.

![image](./images/s3_8_1.png)
![image](./images/s3_8_2.png)

---

### Output Waveform
Analyzing switching waveform.

![image](./images/s3_9.png)

---

### Rise/Fall Time Calculation
Measuring transition delays.

![image](./images/s3_10_1.png)
![image](./images/s3_10_2.png)
![image](./images/s3_10_3.png)
![image](./images/s3_10_4.png)

---

### Cell Delay Calculation
Computing propagation delay.

![image](./images/s3_11_1.png)
![image](./images/s3_11_2.png)

---

## Section 4: Integration & Timing Analysis
Integration of custom cell into design.

### Track Grid Alignment Check
Verifying layout alignment.

![image](./images/s4_1.png)

---

### Generate LEF
Creating abstract view of cell.

![image](./images/s4_3.png)

---

### Modify config.tcl
Updating OpenLANE configuration.

![image](./images/s4_5.png)

---

### Re-run Synthesis with Custom Cell
Including new cell in synthesis.

![image](./images/s4_6_1.png)
![image](./images/s4_6_2.png)


---

### Run Floorplan + Placement
Executing placement flow.

![image](./images/s4_7.png)

---

### Pre-STA Setup
Preparing timing analysis.

![image](./images/s4_9.png)

---

### Run STA (OpenSTA)
Performing timing checks.

![image](./images/s4_10_1.png)
![image](./images/s4_10_2.png)
![image](./images/s4_10_3.png)
![image](./images/s4_10_4.png)
![image](./images/s4_10_5.png)

---

### Timing Optimization
Improving slack values.

![image](./images/s4_11.png)

---

### Run CTS
Generating clock tree.

![image](./images/s4_14_1.png)
![image](./images/s4_14_2.png)

---

### PDN Generation
Creating power network.

![image](./images/s4_16_1.png)
![image](./images/s4_16_2.png)
![image](./images/s4_16_3.png)
![image](./images/s4_16_4.png)

---

## Routing
Connecting all nets.

### Run Routing
Performing detailed routing.

![image](./images/s5_1.png)

---

### Routed Layout
Viewing final routing.

![image](./images/s5_2_1.png)
![image](./images/s5_2_2.png)

---

## Post-Route Analysis
Final verification and timing.

### SPEF Extraction
Extracting parasitics.

![image](./images/s6_1_1.png)
![image](./images/s6_1_2.png)

---

### Post-Route STA
Analyzing timing with parasitics.

![image](./images/s6_2.png)

---

### Final Timing Report
Generating final timing results.

![image](./images/s6_4_1.png)
![image](./images/s6_4_2.png)


---
