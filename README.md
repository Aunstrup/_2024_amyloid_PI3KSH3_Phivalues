# _2024_amyloid_PI3KSH3_Phivalues
Preliminary Github repository for the paper: The mechanism of amyloid fibril growth from Φ-value analysis

This repository contains a Jupyter notebook and data for reproducing the thermodynamic analysis of fibril stabilities for the manuscript: The mechanism of amyloid fibril growth from Φ-value analysis.

# System requirements
The software requires python version 3.8 or higher.

# Installation guide
To open the Notebook, install Miniconda and make sure all required packages are installed by issuing the following terminal commands

    conda create -n --environmentname
    source activate --environmentname

Or open the Notebook in an existing conda environment.

Ensure that all dependent packages and libraries are installed: pandas, numpy, matplotlib, math, lmfit and scipy. These can be controlled by issuing the following commands in the conda-environment

    conda search --packagename

If any packages are not installed run a pip installation by issuing the following command in the conda-environment

    conda install package-name

# Instructructions
In order to run the analysis, open the Notebook and run all cells. 
The code should output 20 sets of fitting parameters, m and s parameters are globally shared and should only take one value. g parameters are local and should only be shared among WT samples, as denoted by the list called 'mutant_label'. All parameter sets correspond to the respective index (using 1-indexing) of the 'mutant-label' list. 
The code should further output a plot of all normalized protein solubility data-points as well as the fitted denaturation curves. 
The code can be expected to have a runtime of approximately 20 minutes on a regular desktop computer.
