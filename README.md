# Spatiotemporal Analysis of Malaria Incidence Trends in Kitui County, Kenya (2023–2025)

## Project Overview
This computational epidemiology pipeline automates the processing, extraction, and compilation of multi-year malaria incidence data from satellite raster layers (`.tiff`) across vector administrative boundaries (`.shp`). 

This specific project is focused entirely on **Kitui County malaria trends for the years 2023, 2024, and 2025**, providing granular, sub-county level insights into shifting transmission dynamics.

## Methodology & Structural Features
- **Spatial Masking**: Dynamically reads and parses local vector shapefiles utilizing `GeoPandas`, filtering data exclusively down to the 40 administrative wards of Kitui County.
- **Defensive Error Handling**: Employs an inline `NoneType` and key-missing validation loop (`[x.get("mean") if x is not None else None for x in stats]`) to handle unpopulated pixels or geometric edge-mismatches safely without triggering pipeline crashes.
- **Temporal Alignment**: Isolates and processes the exact historical observation periods (**2023, 2024, and 2025**) directly from filename string structures.
- **Granular Aggregation**: Uses Pandas to aggregate spatial records into true sub-county arithmetic averages, dropping missing spatial records (`NaN`) natively.
- **Trend Visualization**: Renders publication-ready, multi-year grouped bar charts via `Matplotlib` for comparative regional assessments across Kitui's sub-counties.

## Technologies & Libraries Used
- **Language**: Python 3.x
- **Geospatial Processing**: `geopandas`, `rasterstats`
- **Data Manipulation**: `pandas`, `numpy`
- **Visualization**: `matplotlib`

## Pipeline Output Sample
*(Once you save your bar plot graph as an image, you can drop it here to showcase your results visually!)*
