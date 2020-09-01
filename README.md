# DynaMoE

Model from:  
Tsuda B, Tye KM, Siegelmann HT, Sejnowski TJ. *A modeling framework for adaptive lifelong learning with transfer and savings through gating in the prefrontal cortex.* Preprint bioRxiv:2020.03.11.984757, 2020.
https://www.biorxiv.org/content/10.1101/2020.03.11.984757v1

Rough version of single gating network with 1-3 expert networks

Trains by reinforcement learning with A3C training algorithm of Minh et al. 2016: http://proceedings.mlr.press/v48/mniha16.pdf

Created with Wisconsin Card Sorting Task environment  

**For lesion studies**  
Loads a network that was trained sequentially on shape->color->number with new expert network added in each sort rule (n1->n2->n3), then gating network (dnet) was trained on classic interleaved WCST with all experts present.  
Lesion indicated is implemented and the network is tested on the classic WCST or using the deck from MWCST (no ambiguous cards).

Command to run DynaMoE (currently set up to load a previously trained DynaMoE and test with lesions):  
`python3 DynaMoE_LESION.py [NETSZ_D] [NETSZ_E] [trainenv] [EPS_TO_TRAIN_ON] [GPU] [LTYPE] [p_abl] [carddeck] [runnum]`
