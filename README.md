# [MSc in Modelling for Global Health Thesis Code](https://github.com/1080533/AnophelesMasterThesis/tree/main) 
AnophelesModel is an R package developed by the Analytics and Intervention Modelling Group at Swiss TPH for quantifying the impact of vector control interventions according to mosquito species characteristics. It can be used to parameterize a dynamic model of the mosquito feeding cycle using data about mosquito bionomics (entomological characteristics) and biting patterns, as well as human activity and intervention effects. The different types of data have been extracted from field studies and are included in the package. The model infers the species-specific impact of various vector control interventions on the vectorial capacity. The package can be used to compare the impact of interventions for different mosquito species and to generate geographic-specific parameterizations for the entomological and vector control components of more complex models of malaria transmission dynamics.

This package is associated with the following manuscript:
Golumbeanu et al. AnophelesModel: An R package to interface mosquito bionomics, human exposure and intervention effects with models of malaria intervention impact. bioRxiv. 2023. Available from: https://doi.org/10.1101/2023.10.17.562838

The data and scripts used for generating Figures 2-6 in the manuscript are located at https://github.com/1080533/AnophelesMasterThesis/tree/main/extdata/thesis_scripts .
Figure 2 was generated using the script named "gambiae_stephensi_bionomics.R". Figure 3 was generated using biting pattern data inputted in the same script.
Figure 4 was generated using the script named "gambiae_stephensi_impact.R".
Figures 5 and 6 were generated using the script named "anopheles_sensitivity.R".

The scripts used to integrate human exposure to mosquitoes as a new input parameter, called "specified_multiplier", for the package's "def_intervention_effects" function are located at https://github.com/1080533/AnophelesMasterThesis/tree/main/extdata/thesis_scripts and https://github.com/1080533/AnophelesMasterThesis/tree/main/R .
The "get_in_out_exp" function with the added forced exposure coefficient parameter ("specified_multiplier") was first revised in the script named "get_exposure.R" and copied to the script named "AnophelesModel_db_query.R".
The "calc_interv_effects_db" function used to initialise the effects of an intervention object was revised to accept the "specified_multiplier" input parameter in the script named "internal_intervention_init.R".
The "indoor_outdoor" variable calculated via the "get_in_out_exp" function was revised to accept the "specified_multiplier" parameter in the script named "internal_intervention_models.R". The "calc_LLINs_p" and "calc_IRS_p" functions were then revised to accept the "specified_multiplier" input parameter in the same script.
The "def_intervention_effects" used to define intervention effects for the final entomological model given the specified parameterisations was revised to accept the "specified_multiplier" input parameter in the script named "AnophelesModel_init.R".

To install the package:
```{r}
remotes::install_github("1080533/AnophelesMasterThesis", build_vignettes = TRUE)
```
Note: To be able to build the vignette during package installation, you need to have the following packages installed: remotes, DiagrammeR, ggpubr, ggplot2, and Hmisc.

To load the package:
```{r}
library("AnophelesModel")
```
