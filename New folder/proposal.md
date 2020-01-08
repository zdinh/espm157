ESPM 157 Final Project Proposal

Identification of top marine aquaculture countries and region of interest (ROI) generation 
for future satellite imagery acquisition 

Zack Dinh & Erik Ortega

We propose to identify the top countries engaged in marine aquaculture, generate buffers of their coastal waters, and display these countries and buffers on a webpage. The purpose of this project is to generate regions of interest (ROIs) that in the future will be used by Zack to request high-resolution satellite imagery from a satellite imagery API. The questions we’d like to answer are: 1) what are the top countries engaged in marine aquaculture (specifically floating cage aquaculture), 2) how much each country has produced over time, 3) what is the total surface area of the ROIs.

The United Nations Food and Agriculture Organization (UN FAO) publishes data on global aquaculture production. We plan to identify the top countries using a similar workflow as the fisheries module. The shapefiles of the identified countries will then be extracted from the rworldmap R package. It will be necessary to identify a method to buffer just the coastline of a country’s shapefile, and also to buffer exclusively out towards sea, and not inland. The maximum buffer distance will be no more than 22.2 kilometers, the internationally accepted extent of a country’s territorial waters. We’d like to create a website with an interactive world map displaying the identified countries, coastal buffers, and figures (total square kilometers, marine aquaculture rank, etc.)

An additional step we’d like to pursue is the generation of a country’s coastline from raw data in order to create a very accurate land mask. In the future this land mask will be used by Zack to reduce total search area and prevent false-positives when performing an over-water object detection search for floating aquaculture sites. A highly accurate landmask is considered necessary for this task since many floating aquaculture sites are located close to shore, in bays and inlets that are often deemphasized in basic outline shapefiles such as rworldmap. 

To generate a land mask we propose to create a normal buffer of one country’s coastline (or a section of coastline) and send this ROI to the United States Geological Survey API to download elevation data sourced from the ASTER Global Digital Elevation Model. This 30-meter resolution satellite-derived raster dataset would be reclassified using R. Pixels equal to zero (water) would be eliminated, pixels greater than 1 (land) would be converted to a shapefile to produce the landmask. The reclassification process has been attempted with ASTER data in ESRI ArcMap with excellent results. 

Data Sources
UN FAO aquaculture statistics (CSV)
http://www.fao.org/fishery/statistics/global-aquaculture-production/en

rworldmap country outlines (shapefile)
https://cran.r-project.org/web/packages/rworldmap/index.html

ASTER Global Digital Elevation Model (raster)
https://earthexplorer.usgs.gov/
https://earthexplorer.usgs.gov/inventory/documentation/json-api
