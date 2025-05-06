##  Workflow Overview

This project — *Excitonic Properties of Monolayer Black Phosphorus: Critical Role of Electronic Exchange* —  
follows a four-step workflow to analyze UV-Vis spectra, binding energies, and excitonic properties using hybrid functionals and TDDFT methods.

---

###  **Step 1 — Geometry Optimization with PBE_sol**

Optimize the initial crystal structure using the **PBE_sol** functional.

- **Input**: CP2K `optimize_type` input file  
- **Output**: Optimized structure for use in Step 2

---

###  **Step 2 — Re-optimization with Hybrid Functionals**

Use the geometry from Step 1 as input and perform structure optimizations using various **hybrid functionals** (e.g., PBE0, B3LYP, CAM-B3LYP, etc.).

- **Purpose**: Evaluate how the choice of functional influences structure-dependent electronic properties
- **Note**: Since hybrid functional calculations may not converge easily, an `initial-guess` wavefunction (`.wfn`) file is used in the input to assist the SCF convergence process.

---

###  **Step 3 — TDDFT Calculation (50 States)**

Perform **TDDFT** (Time-Dependent Density Functional Theory) calculations on the structures from Step 2.

- **Note**: TDDFT calculations also use an initial guess for improved SCF convergence.
- **Goal**: Obtain excited-state information, including:
  - UV-Vis absorption spectra  
  - Binding energy  
  - Sr index  
  - Natural Transition Orbital (NTO) contributions

---

###  **Step 4 — Data Visualization**

Use `Multiwfn` and Python scripts to visualize and analyze the results.

- Generate `spectrum_curve.txt` and `spectrum_line.txt` for **UV-Vis spectra**  
- Plot binding energy based on the difference between the **fundamental gap** and **optical gap**  
- Analyze the correlation between **Sr index**, **NTO contributions**, and **optical gap**

 **Files**: All raw spectral data are provided in `UV_vis.tar.gz`

---

[🔝 Back to Top](#top)
