# _2024_amyloid_PI3KSH3_Phivalues
Preliminary Github repository for the paper: The mechanism of amyloid fibril growth from Φ-value analysis

This repository contains a Jupyter notebook and data for reproducing the thermodynamic analysis of fibril stabilities for the manuscript: The mechanism of amyloid fibril growth from Φ-value analysis.
This repository further contains structure files, trajectory files and coordination files for MD simulations performed in the manuscript.

# Thermodynamic analysis
All data necersarry to run the Jupyter notebook is contained within the folder "Thermodynamic analysis"

## System requirements
The software requires python version 3.8 or higher.


## Installation guide
To open the Notebook, install Miniconda and make sure all required packages are installed by issuing the following terminal commands

    conda create -n --environmentname
    source activate --environmentname

Or open the Notebook in an existing conda environment.

Ensure that all dependent packages and libraries are installed: pandas, numpy, matplotlib, math, lmfit and scipy. These can be controlled by issuing the following commands in the conda-environment

    conda search --packagename

If any packages are not installed run a pip installation by issuing the following command in the conda-environment

    conda install package-name

## Instructructions
In order to run the analysis, download the datasets: NanoDSF_summary.xlsx, i29a_i53a.csv, i82a_i22a.csv, wt_i77a.csv and the Notebook analysis_script.ipynb. Open the Notebook and run all cells. 
The code should output 20 sets of fitting parameters, m and s parameters are globally shared and should only take one value. g parameters are local and should only be shared among WT samples, as denoted by the list called 'mutant_label'. All parameter sets correspond to the respective index (using 1-indexing) of the 'mutant-label' list. 
The code should further output a plot of all normalized protein solubility data-points as well as the fitted denaturation curves. 
The code can be expected to have a runtime of approximately 20 minutes on a regular desktop computer.

# MD simulation data
The MD simulations are split into simulation of the full fibril structure and simulation of the transition state ensemble. Starting structure, resulting trajectory file and subsequent analysis for the full fibril simulation can be found in the folder "MD simulation - Stable fibril". The phi value bias file, trajectory and plumed output file for the transition state simulation can be found in the folder "MD simulation - Transition state".

## MD simulation - Stable fibril
This folder contains the following files:
Starting structure for the MD simulation: conf.gro
Trajectory file from the MD simulation: NativeContactsRun_conf_run_9_NOPBC.xtc
Jupyter notebook calculating the fibril state contacts: NativeContacts_Fulltraj.ipynb
Output from NativeContacts_Fulltraj.ipynb: SideChainContacts.txt

## MD simulation - Transition state
This folder conatains the following files:
Plumed file used to bias the the simulation based on experimental Φ-values and the SideChainContacts output: plumed_kappa100.dat
Full trajectory file from the simulation with enforced bias: conf_run_K100_NOPCB.xtc
Plumed output file of residue coordination throughout the simulation with enforced bias: COORDINATION_K100
