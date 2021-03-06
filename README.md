# DynaMoE

Model from:  
Tsuda B, Tye KM, Siegelmann HT, Sejnowski TJ. *A modeling framework for adaptive lifelong learning with transfer and savings through gating in the prefrontal cortex.* Proceedings of the National Academy of Sciences, 117 (47), 29872-29882, 2020.
https://doi.org/10.1073/pnas.2009591117

Rough version of single gating network with 1-3 expert networks

Trains by reinforcement learning with A3C training algorithm of Minh et al. 2016: http://proceedings.mlr.press/v48/mniha16.pdf  
Organization of **DynaMoE_lesion.py** is
  - helper fxns
  - definition of network class
  - definition of worker class
      - train fxn
      - get_experience fxn
      - test fxn
  - main
      - definition of parameters and output directories
      - creation of central network
      - creation of training workers
      - creation of testing workers
      - script to deploy workers for training AND testing

Created with Wisconsin Card Sorting Task environment which loads from **WCST_env.py**  

**For lesion studies**  
Loads a network that was trained sequentially on shape&rarr;color&rarr;number with new expert network added in each sort rule (n1&rarr;n2&rarr;n3), then gating network (dnet) was trained on classic interleaved WCST with all experts present.  
Lesion indicated is implemented and the network is tested on the classic WCST or using the deck from MWCST (no ambiguous cards).

Command to run DynaMoE:  
`python3 DynaMoE_lesion.py [NETSZ_D] [NETSZ_E] [TRAIN_ENV] [EPS_TO_TRAIN_ON] [GPU] [LTYPE] [P_ABL] [CARDDECK] [RUNNO]`

# Citation

If you use this repo in your research, please cite:

    @article{Tsuda_2020,
    Author = {Tsuda, Ben and Tye, Kay M. and Siegelmann, Hava T. and Sejnowski, Terrence J.},  
    Title = {A modeling framework for adaptive lifelong learning with transfer and savings through gating in the prefrontal cortex},  
    Journal = {Proceedings of the National Academy of Sciences},  
    Publisher = {National Academy of Sciences},  
    Volume = {117},  
    Number = {47},  
    Pages = {29872--29882},  
    Doi = {10.1073/pnas.2009591117},  
    Year = {2020}}
