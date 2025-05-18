# Manuscript code - Investigating the relative role of dispersal and demographic traits in predictive phylogeography

------------------------------------------------------------------------

> Author: Rilquer Mascarenhas
> 
> Most recent update: 2025-05-17
>
> Available at [Ecography](https://doi.org/10.1111/ecog.07149)
> 
> To cite this code:
> 
> Rilquer Mascarenhas, Ana C. Carnaval. Investigating the relative role of dispersal and demographic traits in predictive phylogeography. https://github.com/rilquer-mascarenhas/ecog.07149_code/. [10.5281/zenodo.12209533](https://doi.org/10.5281/zenodo.12209533). 2024.

------------------------------------------------------------------------

## Data

The empirical data for this manuscript comes from published studies on birds of the Atlantic Forest (AF) of South America. For each study, we summarized all sequences generated. The original list is available as [csv file](./qmd/data/afmtdna_orig) within the `./qmd/data` folder. Each sequence is assigned to an OTU (Operational Taxonomic Unit) based on the taxonomic level investigated in the study. The final dataset (as of Mar 27, 2023) contains 2479 sequences from 34 OTUs across 20 studies.

## Steps

The links below consist of a step-by-step tutorial for the analyses implemented in this manuscript. Original Quarto Markdown files can be downloaded from the `qmd` folder. Commented R scripts can be downloaded from the `R` folder.

1.  [Loading and processing sequence data](./qmd/1_loading.qmd)
2.  [Creating response variable](./qmd/2_response.qmd)
3.  [Creating predictor variables](./qmd/3_predictors.qmd)
4.  [Training Random Forest models](./qmd/4_training.qmd)
5.  [Exploring model results and evaluation metrics](./qmd/5_results.qmd)
6.  [Performing and mapping predictions genetic divergence](./qmd/6_predictions.qmd)

## Setup

The code below lists all the packages used for the manuscript and checks for those not installed. Each package will be attached later as need.

```{r}
packages <- c(# Data manipulation and visualization
              'tidyverse', 'ggforce','viridis','scales','ggthemes','needs',
              
              
              #spatial
              'tidygeocoder','sf','raster','ggspatial','rnaturalearth',
              'geosphere','rgbif','leaflet','htmlwidgets','stars',
              'gdistance','gstat',
              
              
              #popgen
              'rentrez',
              
              #modeling
              'ENMeval','tidymodels','vip','corrr')

for (name in packages) {
  bool <- require(name, character.only = TRUE)
  if (bool==FALSE) {
    install.packages(name, dependencies = TRUE)
  }
}

# Priotitize dplyr over other packages with similar functions (mostly select() from raster)
prioritize(dplyr)

# Installing muscle
if (!require("muscle", quietly = TRUE)) {
  if (!require("BiocManager", quietly = TRUE))
      install.packages("BiocManager")

  BiocManager::install("muscle")
}

# Installing PopGenome
if (!require("PopGenome", quietly = TRUE)) {
  devtools::install_github("pievos101/PopGenome")
}
```
