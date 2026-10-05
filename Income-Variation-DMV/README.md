# Income Variation Across DMV Census Tracts

## Overview

This project examined differences in median household income across **573 census tracts** in the Washington, D.C., Maryland, and Virginia (DMV) region.

The analysis combined spatial analysis, correlation analysis, and multivariate Ordinary Least Squares (OLS) regression to evaluate how education, population density, public transportation use, and demographic and health-related variables were associated with household income.

## Research Question

**Which demographic, socioeconomic, and urban variables best explain variation in median household income across the DMV region?**

## Study Area

The DMV region was selected because it contains substantial socioeconomic variation within a geographically contiguous area, making it useful for examining spatial patterns in income.

Median household income ranged from approximately **$21,700 to $295,200** across the census tracts analyzed.

## Variables

### Dependent Variable

* Median household income (`income`)

### Explanatory Variables

* Bachelor's degree attainment (`ba_pct`)
* Public transportation use (`wrk_ptpct`)
* Population density (`popdensity`)
* Depression rate (`dep_pct`)
* Percentage male (`pct_male`)

## Methods

### Correlation Analysis

A correlation matrix was used to examine relationships between income and the explanatory variables.

The strongest relationships with income included:

* **Bachelor's degree attainment:** positive correlation (r = 0.52)
* **Population density:** negative correlation (r = -0.35)
* **Public transportation use:** negative correlation (r = -0.33)

Education showed the strongest positive association with household income.

### OLS Regression

Five progressively more complex OLS regression models were developed.

The models added predictors in stages:

1. Education
2. Education + public transportation
3. Education + transportation + population density
4. Education + transportation + population density + depression
5. Full model including percentage male

Model performance was evaluated using adjusted R², AIC, BIC, and the F-statistic.

## Results

The preferred model was **Model 4**, which included:

* Bachelor's degree attainment
* Public transportation use
* Population density
* Depression rate

Model 4 explained approximately **37.1% of the variation in median household income** (R² = 0.371; adjusted R² = 0.367).

The full model only increased R² to 0.386, providing limited additional explanatory power while increasing model complexity. Based on model performance and information criteria, Model 4 was selected as the preferred model.

### Education

Bachelor's degree attainment was consistently the strongest predictor of income across the regression models.

In the preferred model, a one-percentage-point increase in bachelor's degree attainment was associated with approximately a **$2,560 increase in median household income**, holding the other variables constant.

### Transportation and Population Density

Public transportation use and population density showed negative relationships with income in the earlier models.

These patterns are consistent with differences between denser urban areas and higher-income suburban areas across the DMV.

### Depression Rate

Depression rate had a relatively weak bivariate relationship with income, but became statistically significant after controlling for education, transportation, and population density in Model 4.

This demonstrates how relationships between variables can change when multiple factors are considered simultaneously.

## Model Diagnostics

Residual diagnostics indicated some limitations in the model.

The residuals-versus-fitted plot showed slight curvature and increasing spread, suggesting potential **non-linearity and heteroskedasticity**.

The Q-Q plot also showed departures from normality in the upper tail, suggesting the presence of potential high-income outlier census tracts.

## Key Findings

* Education was the strongest and most consistent predictor of household income.
* Census tracts with higher bachelor's degree attainment generally had higher median household income.
* Public transportation use and population density were negatively associated with income in several models.
* Model 4 provided the best balance between explanatory power and model complexity.
* Diagnostic plots indicated some non-linearity, heteroskedasticity, and potential high-income outliers.

## Tools

**R**

* Spatial analysis
* Correlation analysis
* OLS regression
* Model comparison
* Statistical diagnostics
* Data visualization

## Skills Demonstrated

* Spatial data analysis
* Census data analysis
* Multivariate regression
* Statistical modeling
* Correlation analysis
* Model selection
* Residual diagnostics
* Data visualization
* Socioeconomic analysis

## Project Files

[View Full project Report]./ghub%20income%20spatial%20analytics.pdf
