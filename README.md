# iSH1474: Genome-scale metabolic model (GEM) of Pseudomonas putida S12
Reference: Sol Han, Dohyeon Kim, Youngshin Kim and Sung Ho Yoon. "Genome-scale metabolic network model and phenome of solvent-tolerant Pseudomonas putida S12"

These codes and data were used to construct iSH1474 and replicate the results presented in the reference paper.

Last update: 2023-12-02
This repository was created by Sol Han (onepine529@konkuk.ac.kr), Department of Bioscience and Biotechnology, Konkuk University, Seoul, Republic of Korea.

#### Software dependencies
* Python 3 (> v3.7) (https://www.python.org/)
* COBRApy v0.29.0 (https://opencobra.github.io/cobrapy/)
* GLPK linear programming solver included in COBRA
* Biopython v1.73 (https://biopython.org/)
* OpenPyXL v3.0.3 (https://openpyxl.readthedocs.io/)

[The followings are just required for dFBA (secion 5)]
* COBRA Matlab toolbox v3.0.4 (https://opencobra.github.io/cobratoolbox/)
* Matlab v9.6 (https://www.mathworks.com/)

This repository consists of the following sections:

## [1. GEM construction](1_GEM_construction)

#### Python Jupyter notebook (gem_construction.ipynb) for
* Construction of the metabolic network model of S12 (iSH1474)

#### Input folder contains
* NC_002947.4.gb: RefSeq genome annotation file of P. putida KT2440
* NZ_CP009974.1.gb: RefSeq genome annotation file of P. putida S12
* blastp_ortho.xlsx: BLASTP search results
* edgar_ortho.xlsx: EDGAR search results
* iJN1463.xml: GEM of P. putida KT2440
* iPAE1146.xml: GEM of P. aeruginosa PAO1

#### Related materials in the reference paper 
* Figure 1. Workflow of the reconstruction of the metabolic network model of P. putida S12

## [2. Generation of biomass equation](2_Biomass_equation)

#### Python Jupyter notebook (biomass_equation.ipynb) for
* Calcuation of GAM and NGAM
* Calculation of compositions of amino acids, deoxynucleotides (dNTPs), and nucleotides (NTPs) 

#### Input folder contains
* S12 protein sequence.txt: RefSeq protein sequence file of P. putida S12
* S12.xlsx: Excel file that organizes the contents of RefSeq genome annotation file of P. putida S12 by gene
* biomass composition.xlsx: Excel file of calculated molar weight for biomass components using supple table S3
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure S1. Determination of GAM and NGAM in iSH1474 using chemostat data of P. putida S12
* Table S3. Biomass equation of iSH1474

## [3. Validation of model predicitons for carbon utilization](3_Carbon_simulation)

#### Python Jupyter notebook (carbon_simulation.ipynb) for 
* Calculation of 203 sole carbon source availability and the accuracy compared to experimental results in metabolic models
* In vivo measurements: result of 190 PM test (BIOLOG) and 13 solvents as sole carbon source (Table 1 in Weber et al. Appl Environ Microbiol, 56:1347-1351,1990)
* In silico predictions: the growth simulations using iSH1474 (S12) or iJN1462 (KT2440)

#### Input folder contains
* iJN1463.xml: GEM of P. putida KT2440
* iSH1474.xml: GEM of P. putida S12
* PM result.xlsx: Excel file that contains 203 carbon sources and growth results of each carbon

#### Related materials in the reference paper
* Figure 4A. Comparison of growth predictions using iSH1474 and experimental growths on 190 carbon sources contained in the phenotype microarray and 13 organic compounds

## [4. Flux simulation](4_Flux_simulation)

#### Python Jupyter notebook (flux_simulation.ipynb) for
* Comparison of flux distribution in the central carbon metabolism of P. putida S12 from in vivo measurements and in silico predictions
* In vivo measurements: the fluxes from 13C-based metabolic flux analysis of S12 (Figure 5B in Blank et al. The FEBS Journal, 275:5173-5190, 2008)
* In silico predictions: the flux simulations using iSH1474 (S12) or iJN1462 (KT2440)

#### Input folder contains
* iJN1463.xml: GEM of P. putida KT2440
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure 4C. Comparison of flux distribution in the central carbon metabolism of S12 from in vivo measurements and in silico predictions
* Figure S3.  Comparison of flux distribution in the central carbon metabolism of P. putida S12 from in vivo measurements and in silico predictions

## [5. Dynamic flux balance analysisA](5_dFBA)

#### Matlab code (dFBA.ipynb) for 
* Dynamic flux balance analysis (dFBA) using iSH1474 for time profiles of biomass and glucose concentration in aerobic batch growth of S12 on glucose as the sole carbon source (Figure 1 in Isken et al. Applied and Environmental Microbiology, 65:2631-2635, 1999)

#### Input folder contains
* batch_culture.txt: time profiles of biomass and glucose concentration in aerobic batch growth of S12 on glucose as the sole carbon source (Figure 1 in Isken et al. Applied and Environmental Microbiology, 65:2631-2635, 1999)
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure 4D. Dynamic flux balance analysis using iSH1474 for time profiles of biomass and glucose concentration in aerobic batch growth of S12 on glucose as the sole carbon source

## [6. Gene essentialiy analysis](6_Gene_essentiality)

#### Python Jupyter notebook (gene_essentiality.ipynb) for 
* Comparison of predicted essential genes of P. putida S12 and KT2440 growing in a minimal glucose medium

#### Input folder contains
* iJN1463.xml: GEM of P. putida KT2440
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure S4. Comparison of predicted essential genes of P. putida S12 and KT2440 growing in a minimal glucose medium
* Table S7. Predicted essential genes of S12 using iSH1474 for aerobic growth on glucose as the sole carbon source

## [7. Simulation of the utilization of organic solvents](7_Solvent_simulation)

#### Python Jupyter notebook (solvent_simulation.ipynb) for 
* Investigation of the maximum theoretical metabolic capacity of S12 growing on toxic organic solvents

#### Input folder contains
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure 5. Model predictions of growth capability of S12 growing aerobically on heptanoate, octanol, styrene, and glucose
