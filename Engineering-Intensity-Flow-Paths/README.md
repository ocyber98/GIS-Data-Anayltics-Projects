# How Engineering Intensity Shapes Flow-Path Structure

## Overview

This GIS and hydrologic modeling project investigates how engineered stormwater infrastructure alters natural flow-path structures across different land-use regimes. The analysis compares width-function distributions among forested, agricultural, and urban watersheds to evaluate how infrastructure changes the spatial distribution of flow lengths and runoff routing.

## Key Concepts

* **Flow-Path Structure:** The spatial pattern of distances that runoff travels across a landscape before reaching a watershed outlet.
* **Width Function:** A hydrologic metric that summarizes the amount of contributing area at incremental flow-path distances from the basin outlet.
* **Engineered Stormwater Infrastructure:** Human-made systems such as pipes, inlets, culverts, and impervious surfaces that collect and route stormwater.

## Project Objectives

1. Compare flow-path distributions across forested, agricultural, and urban watersheds.
2. Evaluate whether highly engineered basins have different flow-length distributions than less-developed basins.
3. Compare peak flow-path distances, distribution spread, and overall flow-path structure across land-use categories.

## Methodology

### 1. DEM Hydrological Conditioning

A **10-meter Digital Elevation Model (DEM)** was used to create a continuous hydrologic surface. Hydrological conditioning, including sink filling or breaching, was performed before flow modeling.

### 2. Basin Selection & Watershed Delineation

Land cover data and stormwater network data were used to identify watersheds representing different levels of engineering intensity.

Flow Direction and Flow Accumulation grids were generated, and pour points were placed at designated basin outlets to delineate the watershed boundaries.

### 3. Width Function Generation

Cell-by-cell flow lengths to each basin outlet were calculated using the flow-direction network.

Custom spatial analysis scripts and zonal histogram tools were then used to quantify the amount of contributing area within discrete flow-distance intervals and generate width-function distributions.

## Key Results

### Forested Watershed

* **Peak Flow-Path Distance:** ~200 distance units
* **Flow-Path Structure:** Broad distribution of flow distances with longer pathways and greater resistance to runoff movement.
* **Role:** Serves as a relatively natural baseline for comparison.

### Agricultural Watershed

* **Peak Flow-Path Distance:** ~160 distance units
* **Flow-Path Structure:** Shorter peak flow distances than the forested watershed.
* **Role:** Represents a watershed with lower engineering intensity but substantial land modification and vegetation clearing.

### Urban Watershed

* **Peak Flow-Path Distance:** ~100 distance units
* **Flow-Path Structure:** The earliest peak among the three watershed types.
* **Role:** High impervious cover and engineered stormwater infrastructure rapidly collect and route runoff toward the outlet.

## Key Findings

The width-function results show a clear shift toward shorter flow-path distances as engineering intensity increases.

| Watershed Type | Engineering Intensity | Peak Flow Distance |
| -------------- | --------------------- | -----------------: |
| Forested       | Low                   |               ~200 |
| Agricultural   | Moderate              |               ~160 |
| Urban          | High                  |               ~100 |

The urban watershed had the shortest peak flow distance, suggesting that engineered drainage networks and impervious surfaces substantially alter natural flow-path structure and route runoff more directly toward watershed outlets.

## Tools & Skills

* ArcGIS Pro
* Digital Elevation Models
* Hydrologic Modeling
* Watershed Delineation
* Flow Direction
* Flow Accumulation
* Flow Length
* Width-Function Analysis
* Raster Analysis
* Spatial Analysis
* Zonal Statistics
* Custom Spatial Analysis Scripts
* Stormwater Infrastructure Analysis
* Land-Use Analysis

## Project Files

[View the full project](https://github.com/ocyber98/GIS-Data-Anayltics-Projects/tree/main/Engineering-Intensity-Flow-Paths)
