# HAND Plugin

**HAND** is a plugin for generating the **Height Above Nearest Drainage (HAND)** raster — the height above the nearest drainage point — from a **Digital Elevation Model (DEM)**, **watershed**, **flow direction raster**, and **drainage network**.

## Description

The plugin computes the HAND raster, which represents, for each pixel of the DEM, the **vertical difference** between its elevation and the elevation of the nearest drainage pixel (the drainage network pixel to which it flows).  
This product is widely used in **flood susceptibility analysis**, **hydrological modeling**, and **floodplain mapping** [cite: 3].

Processing can be executed **locally**, by invoking **Python/Fortran routines**, or through a **backend** that receives the input files via HTTP and returns the resulting GeoTIFF [cite: 4].

## Requirements

* QGIS 3.22+  
* Python 3.9+ (compatible with QGIS/OSGeo4W)  
* GDAL (≥ 3.8) with Python bindings (`osgeo.gdal`)  
* NumPy  
* The decimal separator must be a dot (`.`), not a comma (`,`).

## Usage in QGIS

1. Launch the plugin through the menu: `Plugins → HAND Plugin`.  
2. Select the input files:  
   * **Digital Elevation Model (DEM)** — GeoTIFF raster (Data Type: Float)  
   * **Watershed** — GeoTIFF raster (Data Type: Integer)  
   * **Flow Direction** — GeoTIFF raster (Data Type: Integer)  
   * **Drainage Network** — GeoTIFF raster (Data Type: Integer)  
3. Click the **“Generate HAND”** button.

The plugin will call the HAND routine developed in **Fortran**.  
Upon completion, a **GeoTIFF** containing the HAND result (raster GeoTIFF, Data Type: Float) will be generated and automatically added to the current QGIS project.

## License

**MIT License**  
Copyright (c) 2025 João Vitor Lima & Adriano Paz