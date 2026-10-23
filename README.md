# Double-Wishbone Independent Suspension System - Multi-Physics FEA Suite

A comprehensive computer-aided engineering (CAE) and multi-physics finite element analysis (FEA) project evaluating the structural integrity, dynamic characteristics, fatigue life, and geometric stability of an automotive **Double Wishbone Independent Suspension System**.

---

## Project Overview
This repository contains the complete simulation and validation workflow for a double-wishbone suspension assembly. Modeled with precision in SolidWorks and analyzed across advanced ANSYS Mechanical solvers, the design was subjected to extreme operational boundary conditions to ensure compliance with automotive safety and durability standards.

---

## CAD Assembly & Physical Properties
* **Active Bodies:** 10 components (Upper Arm, Lower Arm, Wheel Connection/Knuckle, Coil Spring, Base, Pins, Fasteners)
* **Total Assembly Mass:** 4.7738 kg
* **Total Assembly Volume:** 1.65376 × 10⁻³ m³
* **Bounding Box Dimensions:** X = 0.3 m, Y = 0.30031 m, Z = 0.52073 m

---

## Key Analysis Modules & Methodology

### 1. Static Structural & Stress Analysis
* **Loading & Boundary Conditions:** Evaluated under an extreme vertical bump load of 7,113 N alongside multi-axis force components (Z = 6,690 N) applied via a remote point on the knuckle assembly.
* **Material Properties:** Structural control arms and linkages were assigned an **Aluminum Alloy** profile (Density: 2,770 kg/m³, Yield Strength: 280 MPa), while the suspension coil spring utilized high-stiffness **Chrome Silicon**.
* **Stress Results:** Maximum equivalent von-Mises stresses reached 1.9475 × 10^8 Pa on the Upper Arm and 1.9549 × 10^8 Pa on the Lower Arm, remaining safely below the material yield limit.
* **Safety Factor:** Achieved a robust minimum static safety factor of **2.5674**.

### 2. High-Cycle Fatigue Life Evaluation
* **Loading Setup:** Implemented **Zero-Based** constant amplitude cyclic loading to replicate severe unidirectional bump impacts.
* **Singularity Management:** Scoped evaluation strictly to the dual control arms to eliminate localized artificial stress singularities.
* **Durability Performance:** Confirmed a minimum fatigue life of **2.188 × 10^7 cycles** against a 1 × 10^9 design life threshold, verifying complete infinite operating life.

### 3. Pre-Stressed Modal Extraction
* **Dynamic Analysis:** Performed modal analysis coupled directly with nonlinear static pre-stress data transferred from the structural solver.
* **Natural Frequencies:** Extracted the first 6 natural frequencies of the assembly, identifying the fundamental natural frequency at **77.38 Hz** and scaling progressively up to 575.75 Hz for Mode 6.

### 4. Eigenvalue Buckling Stability Verification
* **Instability Assessment:** Executed linear eigenvalue buckling linked to the pre-stressed static state, filtering out negative load multipliers.
* **Load Multipliers:** Obtained critical positive Buckling Load Multipliers of **5.462** (Mode 1) and **5.7356** (Mode 2), confirming a wide safety margin against geometric structural buckling.

---

## Mesh & Element Statistics
* **Total Nodes:** 114,542
* **Total Elements:** 68,140
* **Mesh Quality:** Controlled via skewness metrics and face sizing optimization

---

## Software & Technology Stack
* **CAD Modeling & Assembly:** SolidWorks
* **Numerical Simulation & FEA:** ANSYS Mechanical (Static Structural, Modal, Fatigue, and Eigenvalue Buckling modules)

---

## Repository Structure
```text
├── CAD_Models/                # SolidWorks assembly and part files (.sldprt, .sldasm, .step)
├── ANSYS_Project_Files/       # Workbench archive and system files (.wbpz)
├── Reports/                   # Official simulation reports and documentation (.pdf)
└── README.md                  # Project documentation
