# Wetland Extent Tool 2.0 (WET 2.0)
**Spring 2020 JPL Great Lakes Water Resources II** <br>
WET 2.0 Link: https://code.earthengine.google.com/4e250147ec1489dc24a2c5e5042a7f97 <br>
WET 2.0 Training Link: https://code.earthengine.google.com/7a9abfeb59e8e5d5dc351168db3a306b <br>
WET 1.0 Link: https://code.earthengine.google.com/269c018ccfb89c4de64c1da85c7328a4 <br>

Updated December 12, 2021 by Erica Carcelen to replace deprecated random forest function and include the training script. <br>
Created April 3, 2020

The Wetland Extent Tool 2.0 utilizes Landsat 8, Sentinel 2, Sentinel 1 C-SAR to automate wetland classification in the entire Great Lakes Basin at 10 m resolution. The tool allows users to select date ranges and areas for analysis, outputs map visualizations of the classification, generates time series graphs of optical indices, and exports images to the user's Google Drive. Users can change topographic information used in the classification, which is trained and validated against field data from the entire Great Lakes Basin. Options for topographic input include the Dynamic Surface Water Extent (calculated from Landsat 8 data), and SRTM elevation and slope information. A dark object subtraction atmospheric correction for Sentinel-2 Level 1C data is coded and can be utilized for date ranges that are before 2019, where backlogs of Google Earth Engine data  create large gaps in data coverage.

WET 2.0 is able to classify anywhere in the Great Lakes Basin without exceeding processing limits because the random forest classifier uses an image stack for training that is stored as an asset and imported into the tool. The image stack used for training was generated separately using imagery for the entire year of 2019. Users can customize and create an updated training image stack using the WET 2.0 Training script. 

WET 1.0 utilizes Landsat 8, Sentinel 1 C-SAR, and Topographic Wetness Index (TWI) to classify wetlands in the state of Minnesota at 30 m resolution. WET 1.0 included in this repository contains the code from the Spring 2019 Great Lakes Water Resources team and incorporates the GUI employed by the Spring 2020 Great Lakes Water Resources II team. WET 1.0 has the same GUI as WET 2.0 and has the same instructions for use. 

The tool uses a graphical user interface (GUI) so that users can easily add, process, classify, and export data. The interface contains four main parts: 

	1. a panel to set analysis parameters (time range and area of analysis)
	2. a panel to select analysis types (classification, NDVI, etc) and add images to map
	3. a panel to export images to Google Drive
	4. a time series chart generator that creates line graphs based on the user-entered time range, area of analysis, and selected parameter

The three optical indices calculated are the Normalized Difference Vegetation Index (NDVI), Modified Normalized Water Index (MNDWI), and the Tasseled Cap Wetness Greenness Difference (TCWGD), derived from Sentinel-2 MSI 10 m data. The topographic index calculated is the Dynamic Surface Water Extent (DSWE) derived from a combination of Landsat 8 OLI and SRTM. The tool utilizes Sentinel-1 C-SAR VV, VH, VV/VH bands at 10 m. 

## Required Packages
WET's processing and classification uses Google Earth Engine's free and publicly accessible data catalog, in addition to several pre-loaded asset Google Earth Engine files. These are openly shared and already coded into the tool. 
Users do not need to download data, but do need to have a Google Earth Engine account. 

### Parameters
No additional steps need to be taken to modify the code to enable it to run. Users can run the code and interact with the GUI to customize and run analyses. Users may customize the code to change some inputs, however none need to be modified for it run. The user interface contains brief instructions to guide users through their use of the tool.


### Contact
Name(s): Vanessa Valenti | Erica Carcelen | Kathleen Lange | Nicholas Russo <br>
E-mail(s): vvalenti@g.ucla.edu | ericacarcelen@gmail.com | katielange19@gmail.com | nickrusso@g.ucla.edu
