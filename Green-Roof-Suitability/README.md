# Green Roof Suitability Analysis Using GIS

## Overview

This project used GIS and LiDAR-derived elevation data to identify UMBC buildings with roof areas that may be suitable for green roof installation.

Green roofs are vegetative layers installed on rooftops. They can provide shade, reduce roof and surrounding air temperatures, and help moderate the urban heat island effect in areas with limited vegetation.

The main research question was:

**Which UMBC buildings have low-slope, relatively uncluttered, sun-exposed roof areas large enough to make green roofs practical and beneficial?**

## Data

* UMBC LiDAR data
* UMBC aerial photography (2024)
* Building footprints
* DEM and DSM surfaces derived from LiDAR
* Normalized DSM (nDSM)
* Solar radiation estimates for June 1–September 30, 2025

## Methods

### Surface Model Generation

Raw LiDAR data were processed to create a Digital Elevation Model (DEM) representing ground elevation and a Digital Surface Model (DSM) representing the elevation of surfaces such as rooftops.

A normalized DSM (nDSM) was then created by subtracting the DEM from the DSM to estimate building and surface heights.

### Slope Analysis

Roof slope was calculated using the DSM.

Areas with slopes **≤15°** were classified as suitable based on the selected slope threshold, while areas above the threshold were classified as unsuitable.

The analysis focused on buildings with approximately **30–80% flat roof area**.


### Roof Clutter

Roof clutter was estimated using the standard deviation of elevation values from a 4 × 4 focal neighborhood.

Higher variability in elevation was used as an indicator of rooftop obstructions such as HVAC units, vents, and skylights.

An inverse standardization was applied so that areas with greater clutter reduced the overall suitability score.


### Solar Radiation

Solar radiation was estimated using the ArcGIS Raster Solar Radiation tool for the June–September growing season.

The DSM was used as the input surface to account for rooftop elevation and shading.

Outlier values associated with walls and other obstacles were masked using a defined threshold.

The resulting solar radiation raster was standardized using z-score normalization:

**z = (X − μ) / σ**

Standardization allowed solar radiation and clutter to be combined despite having different measurement scales.


### Suitability Index

The standardized solar radiation and clutter layers were combined to create a green roof suitability index.

The building layer was filtered to include buildings with approximately 30–80% flat roof area. This layer was then used to mask the combined suitability raster.

Building-level median suitability scores were calculated using zonal statistics and used to rank the evaluated buildings.


## Results

The analysis identified several buildings with relatively high suitability based on roof flatness, low clutter, and solar exposure.

The **Performing Arts and Humanities Building**, **Information Technology/Engineering Building**, and **Fine Arts Building** had the highest overall suitability among the evaluated larger roof areas.

* Performing Arts and Humanities Building: highest suitability among evaluated roof areas
* Information Technology/Engineering Building: high suitability with large open roof areas
* Fine Arts Building: high suitability with relatively open and low-slope roof areas
* Martin Schwartz Hall: high median suitability score, but its relatively small roof area makes it less practical for a large green roof installation

Some smaller roof sections were excluded from building-level comparisons, including notable roof levels associated with the Performing Arts and Humanities Building, Information Technology/Engineering Building, and Fine Arts Building.

## Existing Green Roofs

UMBC already has several green roofs, including:

* Patapsco Hall
* Interdisciplinary Life Sciences Building (ILSB)
* Administration Building
* Chesapeake Employers Insurance Arena
* Apartment Community Center

The existing green roofs showed approximately **54% flat roof area** in the analysis.

## Key Findings

The results suggest that roof suitability is influenced by more than simply roof flatness. Areas with low slope, limited rooftop clutter, and greater solar exposure were more favorable for green roof installation.

The suitability index provided a way to combine these factors and compare potential locations across campus.

## Tools

**ArcGIS Pro**

* Spatial Analyst
* Raster Solar Radiation
* Slope analysis
* Focal statistics
* Raster standardization
* Zonal statistics
* LiDAR processing
* Spatial analysis

## Skills Demonstrated

* GIS analysis
* LiDAR processing
* DEM/DSM generation
* Raster analysis
* Suitability modeling
* Hydrologic/topographic analysis
* Spatial statistics
* Environmental data analysis
* Data visualization

## Project Files

[View the full project report](./ghub%20green%20roof%20analysis.pdf)
