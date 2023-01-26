# openCIDAR
## Plasmid sequences
Sequences and annotations for all plasmids used in this study are provided in the "plasmid_sequences" folder in GenBank (.gb) format.

## Flow cytometry analysis
The goal of this directory is to capture the entire analysis pipeline for flow cytometry experiments performed as part of this study. The analysis can be reproduced from raw data (.fcs files) to figures by following the steps below.

Experimental procedures are not included here. Experimental procedures are described within the openCIDAR paper (link).

You will need to have Python and R installed to perform this analysis. I used Python v3.9.14 / Visual Studio Code, and R v4.2.1 / RStudio 2022.07.2+576 "Spotted Wakerobin".

### Analysis procedure
1. Clone this repo (kevinwkeating/openCIDAR) onto your computer.

2. Convert raw data from arbitrary units to MEFL using FlowCal.
    * Navigate to "flow_cytometry_analysis/experimental_data"
    * A folder exists for each organism studied. Within those folders, another folder exists for each experimental run. A separate analysis was performed for each run, as the Spherotec calibration beads were measured with each run and are used to calibrate to MEFL on a per-run basis.
    * For each run, execute the "FlowCal_analysis.ipynb" file. This will generate three new ouput folders.
    * Copy the "*_all_events.csv" file from the "FlowCal_MEFL_CSVs" folder into "flow_cytometry_analysis/MEFL_data." These .csv files contain data for all events from the run, concatenated into a single file. These files were too large to upload to GitHub (>25Mb).

3. Analyze data in R and create figures
    * Open the R script "flow_cytometry_analysis/scripts/summary_flow_analysis.Rmd"
    * Run the script
    * Figures (or figure subpanels) will be written out to "flow_cytometry_analysis/outputs". Figure subpanels were compiled and labeled using Abode Illustrator.

## Copy number analysis
ddPCR data analysis was performed in the proprietary QuantaSoft software. Raw data files are too large to upload to GitHub, but the summary files were exported and are included in the "ddPCR" folder.