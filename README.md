# FiSL-Combustion

# Overview

Processing combustion layer data for Landscapes used in simulation models. 

# Process

## Part 1 Point file for combustion
1. Identify fires that occurred in the landscape 1
2. Download Fire perimeters
3. Clip fire perimeters to Landscape boundary
4. Obtain Landsat image for landscape
5. Overlay Landsat Raster with Landscape burned area ()
6. Convert Raster to points for burned area
7. Add unique ID to each point so outputs from EE can be combined into a single dataframe


## Part 2


### GEE

GEE Scripts
1. Script 1
2. Script 2
3. Script 3


Three scripts from Stefano; all of these scripts take a shapefile of burned pixel centroids as the input.  The shapefile needs to have a date of burn, a unique pixel identifier and the year of burn in order to get all the scripts to work.  All the scripts will output csv files which can then be used to predict the R models on and those predictions can be joined back into the shapefile based on each pixel's unique ID and then rasterized. 
1. static_extract. This will extract all 'static variables' such as soils, topographic variables, and vegetation (we considered it static at the time).   https://code.earthengine.google.com/1e1758b0c628edf79aaa61bb36ea4448
2. landsat_extract.  This will extract NDII, NDVI, dNBR, tasseled cap, tree cover, and some other burn indices.  https://code.earthengine.google.com/7f1bf046ce88cca8f8109d8b9f3e2693
3. FWI extract.  This will extract the fire weather information for all burned pixels by using the Day of Burn information. https://code.earthengine.google.com/b9e024b906580e32cf1c8718b3b8df11


All of these scripts take a shapefile of burned pixel centroids as the input.  The shapefile needs to have a date of burn, a unique pixel identifier and the year of burn in order to get all the scripts to work.  All the scripts will output csv files which can then be used to predict the R models on and those predictions can be joined back into the shapefile based on each pixel's unique ID and then rasterized.  

## part 3

Predictive modeling with XGboost (Future)

Use random forest existing models for Aboveground, below ground and depth of burn to predict combustion for landscape 1

### Data that feeds into this 

