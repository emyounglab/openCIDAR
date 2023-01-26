# openCIDAR
## Plasmid sequences
Sequences and annotations for all plasmids used in this study are provided in the GenBank (.gb) format.

## Flow cytometry analysis
The purpose of this repository is to capture the entire analysis pipeline for flow cytometry experiments performed as part of this study. This analysis can be recreated from raw data (.fcs files) to figures by following the steps below.

Experimental procedures are not within the scope of this repository. Experimental procedures are described within the openCIDAR paper (link).

You will need to have Python and R installed to perform this analysis. I used Python vX, run via Visual Studio Code, and R v4.2.1, run via RStudio 2022.07.2+576 "Spotted Wakerobin".

### Analysis procedure
1. Clone the github repo onto your computer drive.

2. Convert data from arbitrary units to MEFL using FlowCal.
    * Navigate to "flow_cytometry_analysis/experimental_data"
    * A folder exists for each organism studied. Within those folders, another folder exists for each experimental run. A separate analysis was performed for each run, as the Spherotec calibration beads were measured with each run and are used to calibrate to MEFL on a per-run basis.
    * For each run, execute the "FlowCal_analysis.ipynb" file. This will generate three new folders.
    * Copy the "*_all_events.csv" file from the "FlowCal_MEFL_CSVs" folder into "flow_cytometry_analysis/MEFL_data." These .csv files contain data for all events from the run, concatenated into a single file. These files were too large to upload to GitHub (>25Mb).

3. Analyze data in R and create figures
    * Open the R script "flow_cytometry_analysis/scripts/summary_flow_analysis.Rmd"
    * Run the script
    * Figures (or figure subpanels) will be written out to "flow_cytometry_analysis/outputs". Figure subpanels were compiled and labeled using Abode Illustrator.