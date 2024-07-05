# Environmental_Impact_Analysis_using_Satellite_Data(Earth Engine Project README)

## Overview

This repository contains scripts to analyze Landsat 8 imagery using Google Earth Engine. It demonstrates fetching Landsat data, calculating vegetation indices (NDVI and EVI), visualizing results on interactive maps using Folium, and conducting change detection analysis.

## Installation

Make sure you have Python 3.x installed. Install the required Python packages using pip:

```bash
pip install folium matplotlib earthengine-api geopy
```

You'll also need to authenticate and initialize the Earth Engine API:

```python
import ee

# Authenticate the Earth Engine API
ee.Authenticate()

# Initialize the Earth Engine API
ee.Initialize()
```

## Usage

### Running the Scripts

1. **Fetching Landsat Imagery:**
   - Adjust the area of interest (AOI) coordinates and date ranges in the scripts as needed.
   
2. **Calculating NDVI and EVI:**
   - Use the provided functions to calculate NDVI and EVI for Landsat images.

3. **Visualizing Results:**
   - Run scripts to generate interactive maps using Folium. Adjust visualization parameters (e.g., palette) as per your analysis needs.

4. **Change Detection:**
   - Execute change detection scripts to compare NDVI between different time periods and visualize changes.

### Examples

#### Example 1: NDVI Visualization

```python
# Example script to visualize NDVI using Folium
import folium
from datetime import datetime

# Define map center and other parameters
map_center = [37.5, -122.1]
m = folium.Map(location=map_center, zoom_start=10)

# Define visualization parameters for NDVI
ndvi_params = {'min': 0.0, 'max': 1.0, 'palette': ['blue', 'white', 'green']}

# Add NDVI layer to the map
ndvi_map_id = ndvi.getMapId(ndvi_params)
folium.TileLayer(
    tiles=ndvi_map_id['tile_fetcher'].url_format,
    attr='Google Earth Engine',
    overlay=True,
    name='NDVI',
).add_to(m)

# Add layer control to the map
folium.LayerControl().add_to(m)

# Save the map to an HTML file and display it
m.save('landsat8_ndvi_map.html')
m
```

#### Example 2: Change Detection

```python
# Example script for NDVI change detection
import folium

# Fetch Landsat 8 images for two time periods
landsat_before = ee.ImageCollection('LANDSAT/LC08/C01/T1_SR') \
    .filterDate('2019-01-01', '2020-01-01') \
    .median()

landsat_after = ee.ImageCollection('LANDSAT/LC08/C01/T1_SR') \
    .filterDate('2021-01-01', '2022-01-01') \
    .median()

# Calculate NDVI for both time periods
ndvi_before = landsat_before.normalizedDifference(['B5', 'B4']).rename('NDVI')
ndvi_after = landsat_after.normalizedDifference(['B5', 'B4']).rename('NDVI')

# Perform change detection
ndvi_change = ndvi_after.subtract(ndvi_before)
ndvi_change_masked = ndvi_change.updateMask(ndvi_change.abs().gt(0.1))

# Display change detection on the map
m = folium.Map(location=[37.5, -122.1], zoom_start=10)
ndvi_change_map_id = ndvi_change_masked.getMapId({'palette': 'FF0000'})
folium.TileLayer(
    tiles=ndvi_change_map_id['tile_fetcher'].url_format,
    attr='Google Earth Engine',
    name='NDVI Change',
    overlay=True,
).add_to(m)

# Add layer control to the map
folium.LayerControl().add_to(m)

# Save the map to an HTML file and display it
m.save('ndvi_change_map.html')
m
```

## Contributors

- **SABA GULL BASHIR**
  - Role: Contributor
  - Contact: [sabagulbashir@gmail.com]
  - Contact: [saba-adgh267](https://github.com/saba-adgh267)

