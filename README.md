# Thermal Photonics & Diffusionics

## Engineering Heat Flux 

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![LaTeX](https://img.shields.io/badge/LaTeX-Ready-blue.svg)](https://www.latex-project.org/)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-green.svg)](https://www.python.org/)

---

## Overview

**Thermal Photonics & Diffusionics** is an open-source graduate-level textbook that bridges the gap between academic thermal metamaterial physics and practical semiconductor manufacturing applications.

As transistor densities increase and 3D chip stacking becomes standard, **heat is no longer a byproduct to be removed—it is a design variable to be controlled with nanometer precision**. This book unifies two parallel revolutions:

| Framework | Focus | Temperature Regime |
|-----------|-------|-------------------|
| **Diffusionics** | Conduction control via metamaterials | T < 300 degC (wafer handling, metrology) |
| **Thermal Photonics** | Radiation engineering via spectral design | T > 600 degC (RTP, annealing, CVD) |

The "transition zone" (300-600 degC) where both mechanisms matter equally represents the critical regime for advanced semiconductor processing.

---

## Key Features

- **Unified Framework**: Treats heat transfer as a dual phenomenon (phonon diffusion + photon emission) with a mode dominance ratio (Gamma) for systematic design decisions
- **Production-Ready Focus**: Design rules, fabrication constraints, and tolerance specifications for manufacturing
- **Comprehensive Examples**: Worked problems targeting real semiconductor challenges
- **Simulation Code**: Python implementations for thermal metamaterial design and analysis
- **Case Studies**: Lessons learned from production environment deployments

---

## Book Structure

### Part I: Foundations (Ch. 1-4)
The physics of thermal transport—establishing theoretical grounding without losing engineering readers.

### Part II: Diffusionics (Ch. 5-9)
The conduction toolkit—transformation thermotics, effective medium theory, thermal diodes, and planar architectures.

### Part III: Thermal Photonics (Ch. 10-13)
The radiative toolkit—spectral engineering, cold mirrors, radiative cooling, and thermophotovoltaics.

### Part IV: Applications (Ch. 14-17)
Semiconductor-specific implementations—smart wafer chucks, laser annealing, thermal camouflage, and failure analysis.

### Part V: Fabrication & Future (Ch. 18-20)
Manufacturing realities—deposition techniques, metrology, and emerging technologies including ML-driven design.

### Appendices (A-E)
Mathematical foundations, material property databases, simulation templates, design rule index, and problem solutions.

---

## Chapter Overview

| Ch | Title | Key Topics |
|----|-------|------------|
| 1 | The Dual Nature of Heat | Phonon vs photon transport, crossover regimes |
| 2 | Temporal Regimes of Thermal Control | Steady-state limits, transient opportunities |
| 3 | Fluctuation-Electrodynamics | Near-field effects, thermal antennas |
| 4 | The Convection Boundary | Scope definition, interface conditions |
| 5 | Transformation Thermotics Mathematics | Jacobian, conductivity tensors |
| 6 | Effective Medium Theory for Engineers | Binary layers, homogenization |
| 7 | The Doublet Metadevice | Switchable control, liquid metal TIM |
| 8 | Thermal Diodes and Rectifiers | Asymmetric flow, phase-change materials |
| 9 | 1D and Planar Architectures | Cartesian translation, ESC integration |
| 10 | Spectral Engineering Fundamentals | Selective emitters/absorbers |
| 11 | Cold Mirrors and Thermal Windows | Dichroic designs, high-T coatings |
| 12 | Radiative Cooling and Shielding | Atmospheric window, multiphysics cloaks |
| 13 | Thermophotovoltaics | Near-field TPV, waste heat recovery |
| 14 | The Smart Wafer Chuck | Zone control, adaptive thermal management |
| 15 | Laser Annealing and Transient Control | Concentrators, pulse shaping |
| 16 | Thermal Camouflage in Metrology | IR hiding, emissivity decoupling |
| 17 | Failure Analysis and Case Studies | Production lessons learned |
| 18 | Manufacturing Thermal Metamaterials | Deposition, QC, process windows |
| 19 | Metrology for Thermal Metamaterials | Characterization, verification |
| 20 | The Active Future | Phase-change, ML design, thermal computing |

---

## Target Audience

- **Semiconductor Process Engineers** facing thermal non-uniformity challenges
- **Thermal Management Engineers** in advanced packaging (2.5D/3D integration)
- **Graduate Students** transitioning from metamaterial physics to applications
- **R&D Teams** evaluating thermal metamaterial integration

---

## Repository Structure

```
thermal-photonics-diffusionics/
|-- chapters/
|   |-- ch01_dual_nature/
|   |-- ch02_temporal_regimes/
|   |-- ...
|   +-- ch20_active_future/
|-- appendices/
|   |-- appendix_A_math/
|   |-- appendix_B_materials/
|   |-- appendix_C_simulation/
|   |-- appendix_D_design_rules/
|   +-- appendix_E_solutions/
|-- figures/
|   |-- ch01/
|   +-- ...
|-- code/
|   |-- simulations/
|   |-- utilities/
|   +-- examples/
|-- problem_sets/
|-- assets/
|   |-- tpd_latex_template.tex
|   +-- tpd_color_scheme.py
+-- README.md
```

---

## Getting Started

### Prerequisites

**LaTeX Distribution:**
- TeXLive 2022+ (recommended)
- MiKTeX 22.1+

**Python Environment:**
```bash
pip install numpy scipy matplotlib pyyaml
pip install jax jaxlib  # Optional: for optimization routines
```

### Compilation

```bash
# Compile a single chapter
cd chapters/ch01_dual_nature/
pdflatex ch01_main.tex
biber ch01_main
pdflatex ch01_main.tex

# Run simulation code
cd code/simulations/
python ch01_crossover_analysis.py
```

---

## Design Philosophy

### The Conduction-Radiation Duality

Every chapter addresses both heat transfer mechanisms through the **mode dominance ratio**:

```
Gamma = q_rad / q_cond = (epsilon * sigma * T^3 * Delta_T) / (kappa * Delta_T / L)
```

| Regime | Gamma Value | Design Priority |
|--------|-------------|-----------------|
| Conduction-dominated | Gamma << 1 | Diffusionics tools |
| Mixed mode | Gamma ~ 1 | Multiphysics co-design |
| Radiation-dominated | Gamma >> 1 | Thermal photonics tools |

### Four-Axis Failure Analysis

Production-ready designs must address:

1. **Interface Axis**: Contact resistance, thermal boundary resistance
2. **Multiphysics Axis**: Thermal-mechanical-electrical coupling
3. **Fabrication Axis**: Process tolerances, material variability
4. **Thermal Budget Axis**: Cumulative thermal exposure limits

---

## Color Scheme

The book uses a consistent thermal-inspired color palette:

| Color | RGB | Purpose |
|-------|-----|---------|
| TPD Cold | (0, 102, 204) | Conduction, low temperature |
| TPD Hot | (204, 51, 0) | Radiation, high temperature |
| TPD Bridge | (102, 0, 153) | Multiphysics phenomena |
| TPD Meta | (0, 153, 76) | Metamaterial designs |
| TPD Warn | (255, 153, 0) | Warnings, failure modes |
| TPD Gray | (128, 128, 128) | Neutral elements |

---

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Areas Seeking Contributions
- Additional worked examples for semiconductor applications
- Experimental validation data
- Translation to other languages
- Simulation code improvements
- Errata and corrections

---

## Citation

If you use this material in your research or teaching, please cite:

```bibtex
@book{TPD2025,
  title     = {Thermal Photonics and Diffusionics: Engineering Heat Flux },
  author    = {[Chern, Jyh-Long},
  year      = {2026},
  publisher = {Open Source},
  url       = {https://github.com/jlchern-251016/thermal-photonics-diffusionics}
}
```

---

## License

This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).

**You are free to:**
- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material

**Under the following terms:**
- **Attribution** — You must give appropriate credit
- **NonCommercial** — You may not use the material for commercial purposes
- **ShareAlike** — Derivatives must use the same license

---

## Acknowledgments

This book builds upon foundational work in transformation thermotics by Liu-Jun Xu and Ji-Ping Huang, diffusionics research by Fu-Bao Yang, and the broader thermal metamaterials community.


---

*"Heat is not waste—it is information waiting to be engineered."*
