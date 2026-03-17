#  The MD→ML Energy Predictor

## What is this Project About?

This project combines OpenMM molecular dynamics simulations and protein machine learning models to construct a model that can guess the energy of a given protein based on OpenMM data. OpenMM data provides classical physics measurements such as the positions, velocites, and forces that will be the core features that supply the model the infomation to guess the energy of small peptides. This project also incldues an introduction to OpenMM portion that allows newcomers to learn about OpenMM before applying it to a novel situation. 


---

##  Biological Problem & Motivation

Understanding how molecular structure relates to function is a central challenge in computational biology. Molecular dynamics simulations provide atomistic insight into physical behavior, while protein embeddings encode sequence-level information. This project explores how these computational tools can be used together to:

* Analyze thermodynamic stability
* Characterize molecular motion
* Generate and study peptide structures

---

## Data Sources

* **Molecular Dynamics Data**: Generated using OpenMM simulations (positions, velocities, forces, temperature, density, energy).
* **Protein Embeddings**: Precomputed embeddings stored as `.pkl` files (`{uniprot_id: (L, 1280)}` format).
* **Amino Acid SMILES**: Custom CSV containing 20 standard amino acids used to generate peptide structures.

---

## ⚙️ Computational Approach

### Workflow Overview

1. **Simulation Analysis**

   * Extract positions, velocities, and forces
   * Convert nested lists → structured DataFrame
   * Compute thermodynamic quantities (pressure, energy)

2. **Statistical Visualization**

   * Scatter plots (properties vs steps)
   * Histograms (distribution of properties)

3. **Thermodynamic Modeling**

   * Apply ideal gas law:
     ( PV = nRT )
   * Relate pressure, density, and temperature
   * Compute internal energy:
     ( U = \frac{3}{2}PV )

4. **Peptide Generation**

   * Convert amino acid SMILES → dipeptides using reaction SMARTS
   * Generate 3D structures with RDKit
   * Export as PDB files

5. **Visualization**

   * Render peptide structures using py3Dmol

---

## 🧪 Route Design & Implementation

This project followed a multi-stage computational route:

* Built pipelines for handling MD simulation outputs
* Designed transformations from nested simulation data → tabular format
* Implemented thermodynamic calculations from first principles
* Developed a peptide generation workflow using reaction SMARTS
* Created visualization tools for both statistical data and 3D structures

---

## 📈 Results Summary

### Key Findings

* Temperature and density stabilize after equilibration
* Energy fluctuates without significant drift, indicating simulation stability
* Pressure and internal energy show a linear relationship consistent with:
  [
  U = \frac{3}{2}PV
  ]

### Example Outputs

* Scatter plots: Temperature, Density, Energy vs Steps
* Histograms: Distribution of thermodynamic variables
* Generated PDB files for 10 dipeptides
* 3D visualizations of peptide structures

---

## 🔍 Interpretation & Limitations

### Interpretation

* Simulation behaves as expected for an equilibrated system
* Ideal gas approximations provide reasonable trends
* Generated peptides demonstrate correct bonding and geometry

### Limitations

* Ideal gas law is an approximation (not fully accurate for condensed phases)
* Peptide generation does not include full biochemical context (e.g., solvent, termini states)
* Embedding analysis limited to precomputed features

---

## 🚀 Next Steps

* Incorporate explicit solvent simulations
* Improve peptide modeling (correct termini, longer chains)
* Apply machine learning models to embeddings
* Compare MD-derived features with embedding-based predictions

---

## 🔁 Reproducibility

### Requirements

* Python 3.x
* RDKit
* OpenMM
* pandas, numpy
* seaborn, matplotlib
* py3Dmol

### Setup

```bash
pip install pandas numpy matplotlib seaborn py3Dmol
# RDKit and OpenMM may require conda:
conda install -c conda-forge rdkit openmm
```

### Run Analysis

1. Clone repository:

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

2. Run notebooks:

```bash
jupyter notebook
```

3. Execute:

* MD analysis notebook
* Embedding analysis notebook
* Peptide generation script

---

## 📁 Repository Structure

```
├── data/
│   ├── protein_embeddings.pkl
│   └── amino_acids.csv
├── notebooks/
│   ├── md_analysis.ipynb
│   ├── embedding_analysis.ipynb
├── scripts/
│   ├── peptide_generation.py
├── outputs/
│   ├── plots/
│   ├── pdb_files/
├── README.md
```

---

## 🔗 Links to Key Files

* 📓 MD Analysis Notebook: `notebooks/md_analysis.ipynb`
* 📓 Embedding Analysis: `notebooks/embedding_analysis.ipynb`
* 🧪 Peptide Generator: `scripts/peptide_generation.py`
* 📊 Output Figures: `outputs/plots/`
* 🧬 Generated PDBs: `outputs/pdb_files/`

---

## 🙌 Acknowledgments

* OpenMM for molecular simulation tools
* RDKit for cheminformatics workflows
* Thank You to Dr. Crabtree at UCD for 

---
