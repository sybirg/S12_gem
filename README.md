# iSH1474: Genome-scale metabolic model (GEM) of *Pseudomonas putida* S12
#### Reference: Sol Han, Dohyeon Kim, Youngshin Kim and Sung Ho Yoon. "Genome-scale metabolic network model and phenome of solvent-tolerant *Pseudomonas putida* S12"

These codes and data were used to construct iSH1474 and replicate the results presented in the reference paper.

#### Software dependencies
* Python 3 (> v3.7) (https://www.python.org/)
* COBRApy v0.29.0 (https://opencobra.github.io/cobrapy/)
* GLPK linear programming solver included in COBRA
* Biopython v1.73 (https://biopython.org/)
* OpenPyXL v3.0.3 (https://openpyxl.readthedocs.io/)

[The followings are only required for dFBA (section 5)]
* COBRA Matlab toolbox v3.0.4 (https://opencobra.github.io/cobratoolbox/)
* Matlab v9.6 (https://www.mathworks.com/)
* Matlab engine for Python v3.7 (https://kr.mathworks.com/help/matlab/matlab_external/install-the-matlab-engine-for-python.html)
* Matlab kernel for Jupyter v0.17.1 (https://github.com/Calysto/matlab_kernel)

#### This repository consists of the following sections:

## [1. Construction of draft GEM](1_Draft_GEM_construction)

#### Python Jupyter notebook (draft_gem_construction.ipynb) for
* Construction of the metabolic network model of S12 (iSH1474)

#### Input folder contains
* NC_002947.4.gb: RefSeq genome annotation file of P. putida KT2440
* NZ_CP009974.1.gb: RefSeq genome annotation file of P. putida S12
* blastp_ortho.xlsx: BLASTP search results
* edgar_ortho.xlsx: EDGAR search results
* iJN1463.xml: GEM of P. putida KT2440
* iPAE1146.xml: GEM of P. aeruginosa PAO1
* raven_model.xml: RAVEN GEM of P. putida S12

#### Related materials in the reference paper 
* Figure 1. Workflow of the reconstruction of the metabolic network model of P. putida S12

#### Contributor
* Dohyeon Kim (kdhgood9637@gmail.com), Konkuk University, Seoul, Republic of Korea
* Sol Han (twaller950529@gmail.com), Konkuk University, Seoul, Republic of Korea

## [2. Calculation of GAM and NGAM](2_GAM_NGAM_calculation)

#### Python Jupyter notebook (calc_gam_ngam.ipynb) for
* Calculation of GAM and NGAM

#### Input folder contains
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure S1. Determination of GAM and NGAM in iSH1474 using chemostat data of P. putida S12

#### Contributor
* Sol Han (twaller950529@gmail.com), Konkuk University, Seoul, Republic of Korea
* Shakra Ahmad (shakrach98@gmail.com), Konkuk University, Seoul, Republic of Korea

## [3. Validation of model predictions for carbon utilization](3_Carbon_simulation)

#### Python Jupyter notebook (carbon_simulation.ipynb) for 
* Comparison of model predictions and experimental growths on 190 carbon sources contained in the phenotype microarray and 13 organic compounds 
* Model predictions: the growth simulations using iSH1474 (S12) or iJN1462 (KT2440)

#### Input folder contains
* PM_result.xlsx: Phenotype microarray (PM) results
* iJN1463.xml: GEM of P. putida KT2440
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure 4A. Comparison of growth predictions using iSH1474 and experimental growths on 190 carbon sources contained in the phenotype microarray and 13 organic compounds

#### Contributor
* Sol Han (twaller950529@gmail.com), Konkuk University, Seoul, Republic of Korea

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

#### Contributor
* Sol Han (twaller950529@gmail.com), Konkuk University, Seoul, Republic of Korea

## [5. Dynamic flux balance analysis](5_dFBA)

#### Matlab code (dFBA.ipynb) for 
* Dynamic flux balance analysis (dFBA) using iSH1474 for time profiles of biomass and glucose concentration in aerobic batch growth of S12 on glucose as the sole carbon source (Figure 1 in Isken et al. Applied and Environmental Microbiology, 65:2631-2635, 1999)

#### Input folder contains
* batch_culture.txt: time profiles of biomass and glucose concentration in aerobic batch growth of S12 on glucose as the sole carbon source (Figure 1 in Isken et al. Applied and Environmental Microbiology, 65:2631-2635, 1999)
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure 4D. Dynamic flux balance analysis using iSH1474 for time profiles of biomass and glucose concentration in aerobic batch growth of S12 on glucose as the sole carbon source

#### Contributor
* Dohyeon Kim (kdhgood9637@gmail.com), Konkuk University, Seoul, Republic of Korea

## [6. Gene essentiality analysis](6_Gene_essentiality)

#### Python Jupyter notebook (gene_essentiality.ipynb) for 
* Comparison of predicted essential genes of P. putida S12 and KT2440 growing in a minimal glucose medium

#### Input folder contains
* iJN1463.xml: GEM of P. putida KT2440
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure S4. Comparison of predicted essential genes of P. putida S12 and KT2440 growing in a minimal glucose medium
* Table S7. Predicted essential genes of S12 using iSH1474 for aerobic growth on glucose as the sole carbon source

#### Contributor
* Sol Han (twaller950529@gmail.com), Konkuk University, Seoul, Republic of Korea

## [7. Simulation of the utilization of organic solvents](7_Solvent_simulation)

#### Python Jupyter notebook (solvent_simulation.ipynb) for 
* Investigation of the maximum theoretical metabolic capacity of S12 growing on toxic organic solvents

#### Input folder contains
* iSH1474.xml: GEM of P. putida S12

#### Related materials in the reference paper
* Figure 5. Model predictions of growth capability of S12 growing aerobically on heptanoate, octanol, styrene, and glucose

#### Contributor
* Sol Han (twaller950529@gmail.com), Konkuk University, Seoul, Republic of Korea

***
\- This repository was created and maintained by Sol Han (twaller950529@gmail.com), Department of Bioscience and Biotechnology, Konkuk University, Seoul, Republic of Korea.  
\- Inquiries to Sol Han (twaller950529@gmail.com)  
\- Last update: 2023-12-06
