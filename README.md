## Sparse tree-based clustering of microbiome data
R and Matlab code to implement the methods in:
- Shi Y, Zhang L, Do K, Jenq RR, Peterson CB. (2022+) Sparse tree-based clustering of microbiome data to characterize microbiome heterogeneity in pancreatic cancer. *Journal of the Royal Statistical Society: Series C*

### Authors
Yushu Shi (shiyushu2006@gmail.com)

### File organization

The mixture of finite mixture of Dirichlet multinomial (MFMDM) model without tree information can be implemented using the R package BayesianMicrobiome. The mixture of finite mixture of Dirichlet tree multinomial (MFMDTM) model with tree information can be implemented using the Matlab code provided in MFMDTMmatlab folder. Here we included one simulated dataset from the scenario 5 of the paper. 

#### Code

- `MFMDTM.m`. This is the main function. If you want to have a hierarchical Beta prior on the feature selection parameter w, please specify MFMDTM(0), otherwise, specify MFMDTM(w), where w is the guess of the proportion of features being informative. Here, we recommend using w=0.5 when no further information is known about the data.

- `treefunc.m`. Run MCMC iteration for the model without a hierarchical Beta prior on the feature selection parameter.

- `treefuncHier.m`. Run MCMC iteration for the model with a hierarchical Beta prior on the feature selection parameter.

- `treefunc.m`. Select features for the model without a hierarchical Beta prior on the feature selection parameter.

- `treefuncHier.m`. Select features for the model with a hierachical Beta prior on the feature selection parameter.

- `treelikelihood.m`. Calculate likelihood ratio change in add-delete-swap algorithm.

- `treeassign.m`. Assign observations to clusters.

- `simplesplitmerge.m`. Perform simple random split-merge algorithm.

- `launchsplitmerge.m`. Perform restricted Gibbs sampling split-merge algorithm.

- `ll2vs1.m`. Help function for restricted Gibbs sampling split-merge algorithm.

- `drchrnd.m`. Function for generating samples from Dirichlet distribution.

- `logPoissonK.m`. Return log Poisson density function used in the MFM model.

- `logV.m`. Calculate constant terms used in the MFM model.

#### Output Files

- `crec.mat`. MCMC samples of the observation assignment through iterations.
- `gammarec.mat`. MCMC samples of the feature selection through iterations.

#### Input Files
- `phylotreestructure.mat`. A binary matrix showing the topology of the phylogentic tree. Rows correspond to all parent nodes, while columns correspond to children nodes. If there is a linkage between a parent node and a child node, the corresponding entry is one.

- `scenario_5`. 30 simulated observations for scenario 5. Each entry of the matrix shows how many sequence counts passing from a parent node to its child node.

#### Acknowledgements

The code provided here is associated with the following publication and webpage:

- Shi Y, Zhang L, Do K, Jenq RR, Peterson CB. (2022+) Sparse tree-based clustering of microbiome data to characterize microbiome heterogeneity in pancreatic cancer. *Journal of Royal Statistical Society: Series C*

- Code for generating samples from Dirichlet distribution [https://searchcode.com/codesearch/view/2391565/](https://searchcode.com/codesearch/view/2391565/)


