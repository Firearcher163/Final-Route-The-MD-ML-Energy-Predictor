#  The MD→ML Energy Predictor

## What is this Project About?

This project combines OpenMM molecular dynamics simulations and protein machine learning models to construct a model that can guess the energy of a given protein based on OpenMM data. OpenMM data provides classical physics measurements such as the positions, velocites, and forces that will be the core features that supply the model the infomation to guess the energy of small peptides. This project also incldues an introduction to OpenMM portion that allows newcomers to learn about OpenMM before applying it to a novel situation. 


---

##  Biological Problem & Motivation

Understanding how molecular structure relates to function is a central challenge in computational biology. Molecular dynamics simulations provide atomistic insight into physical behavior, while protein embeddings encode sequence-level information. This project explores how these computational tools can be used together to:

* Analyze thermodynamic stability
* Characterize molecular motion
* 

---

## Data Sources

* **Xenon**: Xenon-pdb and xml forces. Courtesy of Dr. Crabtree from UCD.
* **RCSB PDB**: All PDB files came raw from the RCSB PDB in the PDB_Six_Peptides.zip
* **Amber and tip3d**: Standard Protein and Water Force Field Environement.Courtesy of Amber.

---

## Links to Key Files

* Solution Notebook: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Do_William_Final_Solution_CHEM269%20(1).ipynb
* Route Document: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Do_William_Final_Route_CHEM169_269.pdf.docx
* Xenon-27 Cube PDB: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%200-2%20Materials/xe-27.pdb
* Xenon Force Field: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%200-2%20Materials/xenon.xml
* Amber Force Field (Proteins): https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%203-5%20Materials/amber14-all.xml
* Amber Force Field (Water): https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%203-5%20Materials/tip3p.xml
* RCSB PDB Six Peptide Files: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%203-5%20Materials/PDB_Six_Peptides.zip


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
