# Carbon---Endotherm-Diversity-Paper

Files required for analysis reported by Beaudrot et al. analysis of the relationship between carbon storage and ground-dwelling endotherm diversity at 14 TEAM sites

All data are publically available at www.teamnetwork.org/data

######### ANALYSIS & FIGURES ##########

Plant Animal Modeling.R combines all response and predictor variables into single object for use in modeling, runs models and produces figures. See below for calculation of inputs.

########## RESPONSE VARIABLES ##################

SPECIES RICHNESS
RichnessLoop.R estimates species richness for each TEAM site
Uses helper functions to format TEAM data (file = camera trap analysis functions.R)
Parallelizes analysis using file "bugsParallel.r" written by Mathias Tobler
Runs Dorazio's 2006 model (file = "MultiSpeciesSiteOccModel.txt")
Produces input file for use in "Plant Animal Modeling.R""

TAXONOMIC DIVERSITY
WPI_Extraction.R extracts the occupancy weights for each species to use in Shannon Index calculation
Requires WPI output files ("year_effects.csv", "all_effects.csv", "psi_species_model_binomial_last1000.csv", "psi_species_simplemodel_last1000.csv", "psi_species_model_const-phi-gam-p_last1000.csv") and taxonomy file ("taxonomy_scientific_name_wpi_20140414_LB.csv")
Produces input file for use in "Plant Animal Modeling.R""

FUNCTIONAL DIVERSITY
FunctionalDiversity_Overall.R
Uses helper functions to fill in missing values (file = FunctionalTrait_HelperFunctions.R)
Uses Pantheria trait data (file = Pantheria_Data_WR05_Aug2008.csv)
Produces input file for use in "Plant Animal Modeling.R""

########## PREDICTOR VARIABLES #################

PlantDiversity.R calculates genus richness, stem density, carbon storage and other plant variables.
Requires the vegetation database, wood density data (file = GlobalWoodDensityData.csv), Environmental layer from Chave et al. 2015 (file = E_extract_ChaveInPress.csv)
Produces input file for use in "Plant Animal Modeling.R"
Additional predictor variables from other data sources (e.g. latitude, rainfall, forest loss) are aggregated in the file "Plant Animal Modeling.R"

