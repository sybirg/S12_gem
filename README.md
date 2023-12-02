# Genome-scale metabolic network model and phenome of solvent-tolerant Pseudomonas putida S12

These python and MATLAB codes were used to reconstruction of draft model and metabolic flux simulation in this study.

#### software dependencies
* python 3.10.9
* cobrapy 0.29.0
* solver = glpk

Last update: 2023-12-02
This repository was created by Sol Han (onepine529@konkuk.ac.kr), Department of Bioscience and Biotechnology, Konkuk University, Seoul, Republic of Korea.


This repository of S12_gem consists of five source code parts:

## Biomass adjustment
Between P. putida S12 and KT2440, there are genetically and phenotypically differences and such differences were reflected in the biomass equation of the model and corrected specifically for S12.

In order to apply the changes to the model using the corresponding code, the molar fractions must be calculated in the following process.
* The calculation formula is provided in the corresponding Excel file: 'Supplementary Table S3. iSH1474 biomass'
* In 'Macromolecular' tab, enter the experimentally (or in theory) discovered fraction of each macromolecue.
* We modified the information on the three parts of DNA, RNA, and aminoic acid, and calculated the molar ratio of each. Enter the 'Number of bases', 'RNA bases', and 'Total codons per aa'.
* In 'Biomass_WT' tab, automatically-calculated 'mmol/gDW (Calc.)' column is used to make 'biomass composition.xlsx'

More detailed information are annotated in the code and publication.
we provide example files.


## Figure 1: model reconstruction
The reconstruction of draft model using homologous search files, metabolic models and genome of reference strains.

Preparations are as follows:
* Genome files of target- and reference organism
* Homologus search files using EDGAR and BLASTP software
* Reference genome-scale metabolic model (GEM)

If reference GEMs have old locus tag, change the locus tag of orthologous data to the old locus tag of the GEMs

Input GEMs with orthologous data. And get reactions from reference GEMs.

The script was written in Python 3.7.

The dependent packages are as follows:
* COBRApy (https://opencobra.github.io/cobrapy)
* Biopython (https://biopython.org)
* OpenPyXL (https://openpyxl.readthedocs.io/en/stable)

More detailed information are annotated in the code file and we provide example files.
As a result, P. putida S12 has 1,349 metabolic genes as homologous with P. putida KT2440 and 2,842 associated metabolic reactions were retrived from gem of KT2440. And 18 homologs of P. putida S12 were identified in the P. aeruginosa PAO1, which were not observed in the KT2440 GEM, and their 31 associated metabolic reactions were contained to draft. 


## Figure 4C, supplementary figure 3: central metabolism simulation
We provide a script to simulate central carbon metabolism using the completed model and reference model.
The result is provided pandas table and gives the Pearson correlation coefficient value in the last row.

To simulate the flux using this code, costum the file link which you download the model.


## Supplementary figure 4: essential gene
Knockout is performed on all genes included in the model, and if the growth is less than 5% of the normal state, it is determined that there is no growth and predict the genes essential for growth.

To find the essential genes using this code, costum the file link which you download the model.


## Dynamic simulation
Dynamic flux balance analysis (dFBA) simulation

Preparations are as follows:
* Genome-scale metabolic model (GEM)

The “dynamicFBA” function is performed to simulate dFBA

The script was written in MATLAB v9.6.

The dependent packages are as follows:
* The COnstraint-Based Reconstruction and Analysis Toolbox v3.0.4

More detailed information are annotated in the code file.

Using this code, we ran dFBA simulation of iSH1474 (pseudomonas putida S12 GEM).
