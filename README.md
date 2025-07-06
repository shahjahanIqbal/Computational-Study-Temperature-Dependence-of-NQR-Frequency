# Temperature Dependence of NQR Frequency in Plant Nutrient-Based Herbicide Compounds

This repository contains the Python code and accompanying documentation for a computational study of Nuclear Quadrupole Resonance (NQR) frequencies and torsional dynamics in chlorine-containing molecular solids.

---

## Project Overview

NQR is a powerful tool for probing molecular dynamics in solids with quadrupolar nuclei. This project applies **Bayer’s method** to estimate torsional frequencies (fx, fy) from experimental NQR data as a function of temperature.

Using a Python-based simulation, the code automates:
- Fitting experimental NQR frequency vs. temperature data
- Extracting zero-temperature resonance frequency (𝜈₀)
- Calculating torsional frequencies fx and fy for each temperature
- Exporting results

---

## Contents

- `NCICP_IAPT.ipynb`: Jupyter notebook implementing the entire analysis, including data processing, polynomial fitting, and Bayer's method calculations.
- `TempDep.csv`: Expected CSV format with two columns: Temperature [K] and Resonant Frequency [MHz].

---

## Methodology

- Fit a 4th-degree polynomial to frequency vs. temperature data.
- Extrapolate to find 𝜈₀ at T = 0.
- Apply Bayer’s theory:
  
  $$
  \frac{𝜈_T}{𝜈_0} = 1 - \frac{3h}{8\pi^2} \left( \frac{1}{A_x f_x \left( e^{\frac{hf_x}{kT}} - 1 \right)} + \frac{1}{A_y f_y \left( e^{\frac{hf_y}{kT}} - 1 \right)} \right)
  $$

- Iterate over a range of fx and fy values to minimize the error between theoretical and observed values at each temperature.
- Output results with error analysis and comparison to reference data.

---

## Requirements

- Python 3
- Libraries:
  - `numpy`
  - `matplotlib`
  - `scipy`

Install using:

```bash
pip install numpy matplotlib scipy
