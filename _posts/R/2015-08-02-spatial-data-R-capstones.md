---
layout: post
title: "Spatial Data Series Capstone Challenges"
date:   2014-01-07
createdDate:   2015-08-01
lastModified:   2017-03-17
estimatedTime: 0.5 - 1.0 Hours
packagesLibraries: [raster, rhdf5, rgdal]
authors: [Leah A. Wasser, Claire Lunch, Kate Thibault, Natalie Robinson]
categories: [self-paced-tutorial]
tags : [ R, HDF5, spatial-data-gis]
mainTag: primer-raster-data-R, intro-hdf5-r-series, intro-hsi-r-series
tutorialSeries: [primer-raster-data-R, intro-hdf5-r-series, intro-hsi-r-series]
description: "This page contains capstone activities that complement several spatial data tutorial series."
permalink: /R/Spatial-Data-Capstones
comments: true
code1: 
image:
  feature: textur2_pointsProfile.png
  credit:
  creditlink:
---


{% include _toc.html %}

These capstone challenges utilize the skills that you learned in the previous 
tutorials in the:

* <a href="{{ site.baseurl }}/tutorial-series/primer-raster-data-r/" target="_blank"> *Primer on Raster Data in R* series</a>,
* <a href="{{ site.baseurl }}/tutorial-series/intro-hsi-r-series/" target="_blank"> *Introduction to Hyperspectral Remote Sensing Data - in R* series</a>, or
* <a href="{{ site.baseurl }}/tutorial-series/intro-hdf5-r-series/" target="_blank"> *Introduction to the Hierarchical Data Format (HDF5) - Using HDFView & R* series</a>.

<div id="objectives" markdown="1">

## Things You’ll Need To Complete This Tutorial
You will need the most current version of `R` and, preferably, `RStudio` loaded
on your computer to complete this tutorial.

### Install R Packages

* **raster:** `install.packages("raster")`
* **rgdal:** `install.packages("rgdal")`
* **sp:** `install.packages("sp")`

[More on Packages in R - Adapted from Software Carpentry.]({{site.baseurl}}/R/Packages-In-R/)

### Download Data

{% include/dataSubsets/_data_Field-Site-Spatial-Data.html %}

## Tutorial Series 
These capstone activities rely on skills learned in the 

* <a href="{{ site.baseurl }}/tutorial-series/spatial-data-types-primer/" target="_blank"> *Primer on Raster Data* series</a>,
* <a href="{{ site.baseurl }}/tutorial-series/intro-hsi-r-series/" target="_blank"> *Introduction to Hyperspectral Remote Sensing Data - in R* series</a>, or
* <a href="{{ site.baseurl }}/tutorial-series/intro-hdf5-r-series/" target="_blank"> *Introduction to the Hierarchical Data Format (HDF5) - Using HDFView & R* series</a>.
 
</div>

## Capstone One: Calculate NDVI for the SJER field sites

The Normalized Difference Vegetation Index (NDVI) is calculated using the equation:

(NIR - Red) / (NIR + Red)

where NIR is the near infrared band in an image and Red is the red band in an image.
 
 
Use the Red (Band 58 in the GeoTIFF files) and the NIR (band 90 in the GeoTIFF files) 
GeoTIFF files to 

1. Calculate NDVI in R.
1. Plot NDVI. Make sure your plot has a title and a legend. 
1. Assign a colormap to the plot and specify the breaks for the colors to 
represent NDVI values that make sense to you. For instance, you might chose to 
color the data into quartiles using breaks at .25,.5, .75 and 1. 
1. Expore your final NDVI dataset as a GeoTIFF. Make sure the CRS is correct. 
1. To test your work, bring it into QGIS. Does it line up with the other GeoTIFFs 
(for example the band 19 tiff). Did it import properly? 



## Capstone Two: Create an HDF5 file

If you have some of your own data that you'd like to explore for this activity,
feel free to do so. Otherwise, use the vegetation structure data that we've provided
in the data downloads for this workshop. 

1. Create a new HDF5 file using the vegetation structure data in
`D17_2013_vegStr.csv` and `D17_2013_SOAP_vegStr.csv`. (Note that previously the
working directory was set to SJER. You'll have to change this to easily access the 
SOAP vegetation data). 
2. Create two groups within a `California` group:
	- one for the San Joaquin (SJER) field site
	- one for the Soaproot Saddle (SOAP) field site.
3. Attribute each of the above groups with information about the field sites. 
HINT: you can explore the <a href="http://www.neonscience.org/science-design/field-sites/" target="_blank">
NEON field sites page</a> for more information about each site. 
4. Extract the vegetation structure data for San Joaquin and add it as a dataset 
to the San Joaquin group. Do the same for the Soaproot Saddle dataset. 
5. Add the plot centroids data to the SJER group. Include relevant attributes for 
this dataset including the CRS string and any other metadata with the dataset.
6. Open the metadata file for the vegetation structure data. Attribute the 
structure dataset as you see fit to make it usable. As you do this, think about 
the following:
	- Is there a better way to provide or store these metadata?
	- Is there a way to automate adding the metadata to the H5 file?


