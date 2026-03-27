# HAND Plugin

**HAND** is a plugin for generating the **Height Above Nearest Drainage (HAND)** raster — the height above the nearest drainage point — from a **Digital Elevation Model (DEM)**, **watershed**, **flow direction raster**, and **drainage network**. Additionally, it generates a **flood-prone area map** based on a user-defined threshold.

## Description

The plugin computes the HAND raster, which represents, for each pixel of the DEM, the **vertical difference** between its elevation and the elevation of the nearest drainage pixel (the drainage network pixel to which it flows).
This product is widely used in **flood susceptibility analysis**, **hydrological modeling**, and **floodplain mapping**.

Additionally, the plugin generates a **flood-prone area map** by classifying areas where HAND values are below the specified threshold as flood-prone.

Processing can be executed **locally**, by invoking **Python/Fortran routines**, or through a **backend** that receives the input files via HTTP and returns the resulting GeoTIFF.

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
3. Specify output paths for the HAND raster and the flood-prone area map, and set the flood threshold (in meters).
4. Click the **"Generate HAND"** button.

The plugin will call the HAND routine developed in **Fortran**.
Upon completion, two **GeoTIFF** files will be generated and automatically added to the current QGIS project:
- The HAND result (raster GeoTIFF, Data Type: Float)
- The flood-prone area map (raster GeoTIFF, Data Type: Byte), where areas below the threshold are classified as flood-prone.

## License

**MIT License**  
Copyright (c) 2025 João Vitor Lima & Adriano Paz