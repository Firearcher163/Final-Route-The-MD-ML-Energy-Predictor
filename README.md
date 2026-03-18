#  The MD→ML Energy Predictor

## What is this Project About?

This project combines OpenMM molecular dynamics simulations and protein machine learning models to construct a model that can guess the energy of a given protein based on OpenMM data. OpenMM data provides classical physics measurements such as the positions, velocites, and forces that will be the core features that supply the model the infomation to guess the energy of small peptides. This project also incldues an introduction to OpenMM portion that allows newcomers to learn about OpenMM before applying it to a novel situation. 


---

##  Biological Problem & Motivation

Molecules don't exist in a vacuum. They exist in environments that applies forces to the molecule. The simulate this reality we can use molecular dynamic simulations and OpenMM. With OpenMM, we can make more accurate and realistic measurements of energies and structral features of molecules. This project hopes to use these features to train a ML model to get more accurate predictions in finding the energy of molecules.

---

## Data Sources

* **Xenon**: Xenon-pdb and xml forces. Courtesy of Dr. Crabtree from UCD.
* **RCSB PDB**: All PDB files came raw from the RCSB PDB in the PDB_Six_Peptides.zip
* **Amber and tip3d**: Standard Protein and Water Force Field Environement. Courtesy of Amber.

---

## Links to Key Files

* Solution Notebook: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Do_William_Final_Solution_CHEM269%20(1).ipynb
* Route Document: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Do_William_Final_Route_CHEM169_269.pdf.docx
* Xenon-27 Cube PDB: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%200-2%20Materials/xe-27.pdb
* Xenon Force Field: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%200-2%20Materials/xenon.xml
* Amber Force Field (Proteins): https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%203-5%20Materials/amber14-all.xml
* Amber Force Field (Water): https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%203-5%20Materials/tip3p.xml
* RCSB PDB Six Peptide Files: https://github.com/Firearcher163/Final-Route-The-MD-ML-Energy-Predictor/blob/main/Ex%203-5%20Materials/PDB_Six_Peptides.zip


## Computational Approach

### Workflow Overview

1. **Tutorial to OpenMM**

   * Work with a simple model Xenon
   * Understand All the Basic Tools of OpenMM
   * Run Our First OpenMM Simulation

2. **Statistical Visualization**

   * Scatter plots (properties vs steps)
   * Histograms (distribution of properties)
   * Show an overall scope of the type of data OpenMM generates and how we can use it.
   * Application to Thermodynamic Model: Ideal Gas Law

3. **Working with Real PDB Files**

   * Use real raw PDB files from the RCSB
   * Filtering them to the ones that work with OpenMM and Amber Fields
   * Apply OpenMM to generate data from real PDB files

5. **Training a ML Model**

   * Use the data from an OpenMM simuation as features to predict the energy
   * Energy is already accuracy calculated using OpenMM
   * Learned about Clustering based on Entry

---

## Route Design & Implementation

This project followed a multi-stage computational route:

* Establish OpenMM fundamentals
* Visualized and Recorded OpenMM data
* Apply the data to othe chemical problems
* Filter real RCSB PDB data for OpenMM
* Construction of a Energy Prdiction ML model

---

## Results Summary

### Key Findings

Scatter Plots and Histrograms of the Flucations of OpenMM Data (In the Notebook)
Generation of Data USing OpenMM
Construction of a Model to Predict Energy of Molecules using OpenMM data

---

## Interpretation, Limitations, and Next Steps

### Interpretation

* I don't think anything conclusive happened in this route as the results are inconclusive.
* At least, this routes establishes how ot use OpenMM proficiently

### Limitations

* Only generated data was used, not experimental
* Relationship betwee physical components and eneries is questionable
* Couldn't generate peptide for Amber

---

##  Next Steps

* Can I use the OpenMM data better to create a more accurate model
* How I can get the Amber forces to work with custom peptides
* How can I visualize the growth of my model using graphs.


---

##  Reproducibility

### Requirements

* Python 3.x
* RDKit
* OpenMM
* pandas, numpy
* seaborn, matplotlib
* py3Dmol
* sklearn

* The notebook should run fine as is.
```

