# Objective Feature Extraction and Scale Selection for Channel Network Identification

## Overview

This project develops an automated method for extracting channel networks from high-resolution LiDAR Digital Terrain Models (DTMs) without relying on manually selected contributing-area or slope-area thresholds.

Traditional channel extraction methods can be sensitive to terrain type, data quality, and subjective threshold selection. This study evaluates an objective framework for identifying channel features across complex landscapes.

## Research Objectives

1. Automatically determine the optimal spatial scale for terrain analysis.
2. Extract channel networks using LiDAR-derived topographic attributes without subjective manual thresholds.
3. Develop a methodology that can be applied across different and complex terrain environments.

## Study Areas & Data

The framework was evaluated in two contrasting environments:

* **Cordon Basin:** A relatively simple catchment structure with complex surface morphology and abrupt changes in slope.
* **Miozza Basin:** A more organized catchment structure with complex terrain features.

The analysis used high-resolution **1 m LiDAR DTMs** along with DGPS field observations of channel heads and channel networks.

## Methods

### Topographic Morphology

Several terrain attributes were used to identify landscape features associated with channels:

* **Minimum Curvature:** Identifies concave terrain associated with valleys and channel pathways.
* **Positive Openness:** Describes the degree to which terrain is exposed or open.
* **Negative Openness:** Identifies enclosed or depressed terrain features.

### Automatic Scale Selection

Kernel size affects how effectively terrain attributes identify channel features. Instead of selecting a window size manually, the study evaluated the skewness of terrain attribute distributions across multiple kernel sizes.

The optimal scale was identified where increasing kernel size stopped producing meaningful increases in skewness, reducing the risk of over-smoothing important terrain features.

### Normalization & Weighting

Terrain attributes were normalized using Quantile-Quantile (QQ) plot thresholds to identify statistically significant areas of extreme curvature and openness.

The normalized attributes were then combined into a **weight matrix** representing the relative importance of terrain morphology for flow convergence.

### Flow Convergence

A modified **Multiple Flow Direction (MFD)** approach based on Quinn et al. (1991) was used to model flow paths.

Rather than distributing flow based only on slope, the flow algorithm incorporated the morphology-derived weight matrix to better represent convergence toward channel features.

### Noise Filtering

Different filtering approaches were applied to the two basins:

* **Miozza Basin:** A majority filter was used to remove isolated pixels and small areas of noise.
* **Cordon Basin:** Local entropy was used to measure randomness in flow directions. Areas with high entropy were treated as noise, while areas with lower entropy were retained as more structured channel flow.

### Network Connection

A least-cost path approach based on Euclidean distance was used to connect isolated verified channel segments to the primary pour point and create a continuous channel network.

## Key Findings

The study demonstrates that channel networks can be extracted more objectively by combining terrain morphology, automated scale selection, flow convergence, and spatial filtering.

The results also show why universal channel-head thresholds can be problematic: both study basins contained channel heads across a wide range of contributing areas.

## Tools & Skills

* LiDAR / Digital Terrain Models
* Terrain Analysis
* Raster Analysis
* Spatial Analysis
* Flow Direction & Flow Accumulation
* Multiple Flow Direction
* Kernel Analysis
* Quantile-Quantile Analysis
* Entropy Analysis
* Least-Cost Path Analysis
* GIS Modeling
* Automated Feature Extraction

## Project Files

[View the full project report](https://github.com/ocyber98/GIS-Data-Anayltics-Projects/blob/main/Engineering-Intensity-Flow-Paths/ghub%20watershed%202.pdf)

