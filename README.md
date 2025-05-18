# [CODE] Investigating the relative role of dispersal and demographic traits in predictive phylogeography

------------------------------------------------------------------------

> Author: Rilquer Mascarenhas
> 
> Most recent update: 2025-05-17
>
> Available at [Ecography](https://doi.org/10.1111/ecog.07149)
> 
> To cite this code:
> Rilquer Mascarenhas, Ana C. Carnaval. Investigating the relative role of dispersal and demographic traits in predictive phylogeography. https://github.com/rilquer-mascarenhas/ecog.07149_code/. [10.5281/zenodo.12209533](https://doi.org/10.5281/zenodo.12209533). 2024.

------------------------------------------------------------------------

## Data preparation

The empirical data comes from published studies on birds of the Atlantic Forest (AF) of South America. We performed a search of published phylogeographic and phylogenetic studies that have generated mtDNA data for birds that occur in the Atlantic Forest. For each study, we highlighted the higher taxonomic level investigated, regardless of whether it was a species, a species complex or a genus. Our goal was to create a model that summarizes and predicts the levels of genetic differentiation observed across studies. Since in some studies that investigation was done based on a taxonomic species, whereas in other it was done based on a species complex or a genus with unresolved species taxonomy, we decided to maintain the taxonomic level of the original study in most cases. This is justifiable considering the resolution of the empirical data generated (in terms of sample size per locality and per lineage, as well as the geographic sampling) matches the taxonomic level used in the paper. Additionally, most of these diverged within 1 million years into the past, and the divergence shown in the study falls within the late Pleistocene period we are trying to investigate. Currently recognized species that are merged into a higher taxonomic level for our study are: *Sclerurus scansor* and *Sclerurus cearensis* (merged into *Sclerurus scansor*, divergence around 600kya) and *Microspingus cabanisi* and *Microspingus lateralis* (merged into *Microspingus*, divergence around 80kya).

Finally, we removed a few nominal species with non-resolved taxonomy or for which intraspecific sampling was thought to not be enough to investigate genetic differentiation generated during the late Pleistocene: *Eleoscytalopus psychopompus*, *Scytalopus diamantinensis*, *Scytalopus iraiensis*, *Scytalopus novacapitalis*, *Scytalopus pachecoi*, *Scytalopus pachecoi* and *Synallaxis infuscata*.

To avoid any confusion, hereinafter we refer to the taxonomic unit we assume as Operational Taxonomic Unit (OTU).

The final dataset (as of Mar 27, 2023) contains 2479 sequences from 34 OTUs across 20 studies. It includes four mtDNA loci: Control Region, ND2, ND3 and CYTB.

## Steps

The links below will lead you to a step-by-step tutorial for the analyses implemented in this manuscript. Original Quarto Markdown files can be downloaded from the `qmd` folder. Commented R scripts can be downloaded from the `R` folder.

0.  [Setup](./qmd/0_setup.qmd)
1.  [Loading and processing sequence data](./qmd/1_loading.qmd)
2.  [Creating response variable](./qmd/2_response.qmd)
3.  [Creating predictor variables](./qmd/3_predictors.qmd)
4.  [Training Random Forest models](./qmd/4_training.qmd)
5.  [Exploring model results and evaluation metrics](./qmd/5_results.qmd)
6.  [Performing and mapping predictions genetic divergence](./qmd/6_predictions.qmd)
