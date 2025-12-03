HAND Plugin

HAND — plugin for generating the Height Above Nearest Drainage (HAND) raster from:
Digital Elevation Model (DEM),
watershed,
flow direction raster, and drainage network.

Description

The plugin calculates the HAND raster, which represents, for each DEM pixel, the vertical difference between the pixel’s elevation and the elevation of the nearest drainage pixel (the drainage network pixel to which it flows).
This product is widely used in flood susceptibility analysis, hydrological modeling, and floodplain mapping.
Processing can be executed locally (by invoking Python/Fortran routines) or through a backend that receives files via HTTP and returns the resulting GeoTIFF.

Requirements

QGIS 3.22+.
Python 3.9+ (compatible with QGIS/OSGeo4W).
GDAL (>=3.8) with Python bindings (osgeo.gdal).
NumPy.
The decimal separator must be a dot (.) and not a comma (,).

Usage in QGIS

Start the plugin from the menu Plugins → HAND Plugin.

Select the inputs:
-Digital Elevation Model - DEM (GeoTIFF raster with Data Type Float)
-Watershed (GeoTIFF raster Data Type Integer)
-Flow Direction (GeoTIFF raster Data Type Integer)
-Drainage Network (GeoTIFF raster Data Type Integer)

Click the Generate HAND button. The plugin will:
Call the HAND routine developed in Fortran.

After completion, a GeoTIFF containing the HAND result (GeoTIFF raster with Data Type Float) will be generated and automatically added to the current QGIS project.

MIT License
Copyright (c) 2025 <João Vitor Lima & Adriano Paz>