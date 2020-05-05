# DynaMoE

https://www.biorxiv.org/content/10.1101/2020.03.11.984757v1

Single gating network with 1-3 expert networks

Uses reinforcement learning with A3C training algorithm of Minh et al. 2016: http://proceedings.mlr.press/v48/mniha16.pdf

Created with Wisconsin Card Sorting Task environment  

**Lesion studies: a3c_btsuda_dnet3seeded_LESION_importENV.py**  
Loads a network that was trained sequentially on shape->color->number with new expert network added in each sort rule, then dnet was trained on classic interleaved WCST with these experts.  
Lesion indicated is then implemented and the network is tested on the classic WCST.
