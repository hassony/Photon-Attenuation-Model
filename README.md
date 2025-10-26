### Unified Empirical and Time-Weighted Models for Photon Attenuation Using XCOM Data

**Author:** Hassan Almoosa
**Year:** 2025
**Affiliation:** Independent Medical Physics Researcher

---

### Abstract

This study presents a unified analytical framework for photon attenuation based on the NIST XCOM database.
The framework integrates three complementary formulations:

1. A global log–linear empirical law describing general photon attenuation behavior.
2. A multi-slope piecewise model distinguishing photoelectric, Compton, and pair production regions.
3. A time-weighted extension that introduces temporal degradation and radioactive decay effects.

The unified empirical–temporal formulation provides a comprehensive model for predicting photon interaction behavior in shielding materials, combining both spatial and temporal dependencies.

---

### Objectives

* Develop and validate empirical attenuation models using XCOM data.
* Introduce time-weighted and separable temporal formulations to describe material degradation.
* Establish correlations between model coefficients and atomic number for generalized prediction.
* Integrate physical decay constants for Cs-137 and Co-60 into the unified attenuation law.

---

### Methodology

The analysis is conducted using Python and scientific libraries (NumPy, SciPy, and Matplotlib).
The workflow includes:

1. Importing NIST XCOM reference data for several materials (Fe, Pb, Al, H₂O).
2. Logarithmic fitting of the empirical relation:
   μ = a·Zᵇ·ρᵈ·E⁻ᶜ
3. Piecewise fitting for low-, mid-, and high-energy regions to obtain {c₁, c₂, c₃}.
4. Establishing correlations between {c₁, c₂, c₃} and log(Z_eff).
5. Extending the attenuation model to include temporal degradation and radioactive decay:
   I(E, Z, ρ, x, t) = I₀ exp[-a·Zᵇ·ρᵈ·E⁻ᶜ(x + βt)] exp(-λt).

All computational steps are contained within the Jupyter notebook file:
**Unified_Empirical_TimeWeighted_Model.ipynb**

---

### Data Source

Reference mass attenuation coefficients were obtained from the **NIST XCOM Photon Cross-Section Database (Version 1.5)**.
The dataset covers photon energies from 1 keV to 100 MeV for elements 1–100 and selected compounds.

Citation for data source:
M. J. Berger and J. H. Hubbell, *XCOM: Photon Cross Sections Database (Version 1.5)*, National Institute of Standards and Technology (NIST), 2025.

---

### Structure of the Notebook

The notebook is organized into the following sections:

1. **Imports and Constants** – Load dependencies, define constants, and setup material parameters.
2. **Empirical Log–Linear Fitting** – Fit and validate the global model against XCOM data.
3. **Two- and Three-Slope Piecewise Models** – Separate photoelectric, Compton, and pair-production regions.
4. **Correlation Analysis** – Relate coefficients {c₁, c₂, c₃} to log(Z_eff).
5. **Time-Weighted Extension** – Introduce β (cm/year) as a temporal degradation rate.
6. **Physical Source Calibration** – Incorporate λ for Cs-137 and Co-60 decay constants.
7. **Sensitivity Analysis** – Study the effect of β on attenuation stability.
8. **Unified Analytical Framework** – Combine all components into one general expression.
9. **Visualization and Discussion** – Generate all figures and tables included in the research paper.

---

### Results Summary

* The empirical model achieved over 90% accuracy when compared to NIST data.
* The piecewise formulation correctly distinguishes dominant interactions across energy regions.
* The correlation analysis shows that c₃ strongly depends on log(Z_eff), confirming pair-production scaling with Z².
* The time-weighted extension successfully models long-term attenuation degradation using realistic β values.
* Integration of radioactive decay constants (λ) for Cs-137 and Co-60 validates the temporal behavior physically.

---

### Figures and Tables

All plots and summary tables are generated automatically within the notebook.
Output figures include:

* Empirical fit comparisons for each material.
* Piecewise model transitions across energy regimes.
* Correlation plots of c₁, c₂, and c₃ versus log(Z_eff).
* Temporal decay and β-sensitivity visualizations.
* Unified framework schematic diagram.

All figures are stored under the directory:
`/figures/`

---

### Citation

If you use or reference this work, please cite it as:

Hassan Almoosa (2025). *Unified Empirical and Time-Weighted Models for Photon Attenuation Using XCOM Data.*
Independent Computational Study. GitHub Repository. Licensed under CC BY-NC 4.0.

---

### Acknowledgments

This work utilizes open-access data from the NIST XCOM Photon Cross-Section Database.
The author acknowledges prior foundational studies in photon interaction modeling by:

* E. Storm & H. Israel (1970)
* J. H. Hubbell (2006)
* A. M. El-Khayatt (2010)
* G. J. Hine & S. R. Sholom (2014)
* G. F. Knoll (2010)

---

### License

This project is licensed under the **Creative Commons Attribution–NonCommercial 4.0 International License (CC BY-NC 4.0)**.
You may share and adapt the material for non-commercial use with proper attribution.

For full terms, see the [LICENSE](LICENSE) file or visit:
[https://creativecommons.org/licenses/by-nc/4.0/](https://creativecommons.org/licenses/by-nc/4.0/)
