

[![Build Status](https://travis-ci.com/espm-157/final-project-aqua-team-erik-and-zack.png)](https://travis-ci.com/espm-157/final-project-aqua-team-erik-and-zack)

## Team Members:

- Zack Dinh, zdinh
- Erik J Ortega, erikjortega

## Final Project Summary
In our project we identify countries that are the greatest producers of marine finfish aquaculture by analyzing data from the United Nations Food and Agriculture Organization (UNFAO). The data, consisting of several CSVs were joined, filtered, grouped, and summarized to identify the total production of finfish, in the marine environment, in tonnes, from 2016, for each country. 

We visualize our findings with bar plots using gggplot2, as well as on a interactive web map using Leaflet. With the SF package we read in a shapefile of the world's countries, select the top 20 for display on the webmap. Additionally, we generate areas of interest (AOIs) polygons of the territorial waters adjacent to each country, defined as waters within 22.2km of the coastline. These AOIs are generated for future use in downloading high-resolution satellite imagery from an API.

We develop a process to generate higher-resolution coastline vectors from elevation data. 30-meter resolution elevation rasters sourced from the United States Geological Survey (USGS) were merged and reclassified with the Raster package. Areas with an elevation greater than 0 are classified as land, while areas less than 0 classified as water. Using rgdal and gdal, we convert the classified raster to a vector. The generation of higher resolution coastlines is intended to function as a mask to exclude land from future satellite image processing focused on the waters within the AOIs.

Lastly, we publish our findings on the internet by hosting our Rmarkdown.html file on github.

## assignment

All work for this assignment should be in the `assignment` directory.  You will work in the `.Rmd` notebook, and commit your rendered output files (`.md` and associated files) in the `assignment` directory as well.

## Special files

All team repositories will also include most of the special files found here:

### Common files

- `README.md` this file, a general overview of the repository in markdown format.  
- `.gitignore` Optional file, ignore common file types we don't want to accidentally commit to GitHub. Most projects should use this. 
- `<REPO-NAME>.Rproj` Optional, an R-Project file created by RStudio for it's own configuration.  Some people prefer to `.gitignore` this file.


### Infrastructure for Testing

- `.travis.yml`: A configuration file for automatically running [continuous integration](https://travis-ci.com) checks to verify reproducibility of all `.Rmd` notebooks in the repo.  If all `.Rmd` notebooks can render successfully, the "Build Status" badge above will be green (`build success`), otherwise it will be red (`build failure`).  
- `DESCRIPTION` a metadata file for the repository, based on the R package standard. It's main purpose here is as a place to list any additional R packages/libraries needed for any of the `.Rmd` files to run.
- `tests/render_rmds.R` an R script that is run to execute the above described tests, rendering all `.Rmd` notebooks. 




