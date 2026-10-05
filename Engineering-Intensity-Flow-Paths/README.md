Objective Feature Extraction for Channel Network Identification

## Overview

This project presents an automated statistical methodology for extracting channel networks from Digital Terrain Models (DTMs) without relying on manually selected thresholds.

Traditional channel extraction methods often use fixed thresholds, such as minimum contributing area or slope-area ratios. These thresholds may overpredict channel heads and perform inconsistently across different terrain types. This workflow reduces subjectivity by analyzing spatial feature distributions to dynamically select analysis scale and identify drainage pathways.

Key Features & Objectives
Objective Scale Selection: Determines terrain analysis window sizes without subjective bias.
Automated Network Identification: Uses LiDAR-derived topographic attributes to identify channel features and drainage networks.
Broad Applicability: Avoids generic fixed thresholds to improve performance across diverse and complex landscapes.
Study Areas

The model was evaluated using high-resolution 1 m LiDAR DTMs and validated against field-mapped channel heads collected using Differential GPS (DGPS).

Basin	Geomorphological Characteristics
Cordon Basin	Simple catchment boundary with highly complex morphology and abrupt slope changes.
Miozza Basin	More organized catchment structure with complex local terrain features.
Methodology
1. Morphology Detection

Two primary terrain metrics were derived from the DTM:

Minimum Curvature: Measures surface concavity and helps identify valleys and potential channel pathways.
Openness: Measures how open or enclosed terrain is relative to its surroundings and captures larger-scale landform patterns.
2. Scale & Kernel Size Selection

The analysis evaluated terrain attributes across different window sizes and used skewness to determine the optimal analysis scale.

Increasing skewness indicates that the selected kernel is enhancing important terrain features such as valleys. The optimal scale was identified where increasing the kernel size stopped producing meaningful increases in skewness, reducing the risk of over-smoothing terrain features.

3. Normalization & Weighting

Q-Q plot analysis was used to identify extreme values within the curvature and openness distributions.

The normalized terrain attributes were then combined into a spatial weight matrix representing the relative importance of terrain morphology for channel identification.

4. Morphologically Weighted Flow Convergence

A modified Multiple Flow Direction (MFD) algorithm based on Quinn et al. (1991) was used to model flow convergence.

Instead of relying only on slope gradients, flow routing was weighted using the morphology-derived matrix. This allowed the model to better represent convergence toward potential channel pathways.

5. Noise Filtering & Network Connection

Different filtering methods were applied to account for differences between the study basins:

Miozza Basin: A majority filter was used to remove isolated noise pixels.
Cordon Basin: Local flow-direction entropy was used to distinguish structured channel flow from chaotic surface noise. Areas with high entropy were filtered out.
Network Connectivity: Isolated channel segments were connected to the main outlet using a Least-Cost Path (LCP) algorithm based on Euclidean distance.
Methodology Pipeline
DTM Data
   ↓
Topographic Metrics
   ↓
Skewness-Based Kernel Selection
   ↓
Q-Q Plot Normalization
   ↓
Morphological Weight Matrix
   ↓
Weighted MFD Flow
   ↓
Noise Filtering
   ↓
Least-Cost Path Connection
   ↓
Final Channel Network
Key Findings

The workflow demonstrates how terrain morphology and statistical analysis can be combined to automatically identify channel networks without relying on universal fixed thresholds.

Using objective scale selection, morphology-based weighting, flow convergence, and spatial filtering provides a more adaptable approach for extracting drainage features from high-resolution terrain data.

Tools & Skills
LiDAR / Digital Terrain Models
ArcGIS / GIS
Raster Analysis
Terrain Morphometry
Spatial Analysis
Multiple Flow Direction
Kernel Analysis
Skewness Analysis
Q-Q Plot Analysis
Entropy Analysis
Least-Cost Path Analysis
Automated Feature Extraction
Hydrologic Modeling

## Project Files
[View the full project report](https://github.com/ocyber98/GIS-Data-Anayltics-Projects/blob/main/Engineering-Intensity-Flow-Paths/ghub%20watershed%202.pdf)

