# Spatial Analysis of Demographic, Environmental, and Infrastructure Factors in Baltimore

## Overview

This project contains three GIS spatial analysis studies conducted in Baltimore City, examining electric vehicle infrastructure, urban tree growth, and impervious surface patterns.

## 1. Electric Vehicle Charging Station Usage

### Objective

Investigate whether age, race, and median household income are associated with the location and usage of electric vehicle (EV) charging stations across Baltimore.

### Methods

* Created 1-mile buffer zones around EV charging stations.
* Used Dissolve and Multipart to Singlepart to simplify buffer geometries.
* Clipped charging station locations to the buffer areas.
* Joined demographic data to the charging station areas.
* Compared age, race, and median household income across the study areas.

### Key Findings

Race, age, and income were not reliable predictors of EV charging station adoption or placement in Baltimore. The results suggest that other factors, such as infrastructure availability, transportation patterns, and commuter behavior, may play a larger role.

## 2. Tree Growth and Railroad Proximity

### Objective

Assess whether proximity to railroad infrastructure is associated with urban tree growth, measured using Diameter at Breast Height (DBH).

### Methods

* Performed a Spatial Join between tree locations and railroad networks.
* Classified tree DBH values into equal intervals.
* Used Kernel Density analysis to visualize spatial patterns in tree DBH relative to railroad proximity.

### Key Findings

Tree DBH showed a statistically significant negative relationship with proximity to rail lines. Smaller trees were more concentrated near railroad infrastructure, while larger DBH values were more common farther from rail lines.

## 3. Impervious Surface Area Analysis

### Objective

Evaluate the spatial distribution and concentration of impervious surface area across Baltimore City census tracts.

### Methods

* Joined Baltimore City census tract boundaries with an impervious surface raster.
* Used Summary Statistics to calculate aggregate impervious surface coverage by tract.
* Classified census tracts based on total impervious surface coverage.
* Identified areas with the highest concentrations of impervious surfaces.

### Key Findings

Impervious surface coverage was heavily concentrated in Baltimore's downtown core and along major transportation corridors. The top 10% of census tracts accounted for approximately 50% of the city's total impervious surface area.

## Tools & Skills

* ArcGIS Pro
* Spatial Join
* Buffer Analysis
* Dissolve
* Multipart to Singlepart
* Raster Analysis
* Kernel Density
* Summary Statistics
* Census Data Analysis
* Spatial Data Visualization
* Environmental & Urban GIS

## Project Files

[View Full Project]

