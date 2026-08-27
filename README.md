# Raster-Clipper-Clip-Raster-Using-Vector
Python tool for clipping raster GeoTIFFs using vector boundaries and generating a PNG preview of the clipped output.

# Raster Clipper

A Python-based GIS utility for clipping a raster dataset using a vector boundary. The program takes the paths of a vector file, raster file, and output file, then generates a clipped GeoTIFF along with a PNG preview of the clipped raster.

## Features

* Clip raster data using a vector boundary.
* Supports common GIS raster and vector formats.
* Saves the clipped result as a GeoTIFF (`.tif`).
* Generates a PNG image preview of the clipped raster.
* Simple command-line workflow.
* Useful for GIS, remote sensing, and geospatial data processing.

## How It Works

The program uses a vector layer as the clipping boundary and extracts the corresponding area from the input raster.

```text
Input Raster + Vector Boundary
              │
              ▼
       Raster Clipping
              │
       ┌──────┴──────┐
       ▼             ▼
  Clipped TIFF    PNG Preview
```

## Requirements

Python 3.8 or newer is recommended.

The project uses common Python geospatial libraries such as:

* `rasterio`
* `geopandas`
* `shapely`
* `numpy`
* `matplotlib`

Install the required packages with:

```bash
pip install -r requirements.txt
```

## Usage

Run the program from the command line by providing:

1. Path to the vector file
2. Path to the input raster
3. Name/path of the output file

Example:

```bash
python raster_clipper.py path/to/vector.shp path/to/input.tif output.tif
```

The program will produce:

```text
output.tif
output.png
```

The `.tif` file contains the clipped geospatial raster, while the `.png` file provides a visual preview of the clipped result.

## Input Data

### Vector

The vector input should contain the boundary used for clipping. Common formats include:

* Shapefile (`.shp`)
* GeoPackage (`.gpkg`)
* GeoJSON (`.geojson`)

### Raster

The raster input should be a georeferenced raster dataset, such as:

* GeoTIFF (`.tif` / `.tiff`)

## Output

The program generates two files:

### Clipped GeoTIFF

The clipped raster retains its geospatial information and can be used in GIS software such as QGIS or ArcGIS.

### PNG Preview

A PNG image is generated to provide a quick visual representation of the clipped raster.

## Example Workflow

Suppose you have:

```text
data/
├── boundary.shp
├── boundary.shx
├── boundary.dbf
├── boundary.prj
└── elevation.tif
```

Run:

```bash
python raster_clipper.py data/boundary.shp data/elevation.tif clipped_elevation.tif
```

Output:

```text
clipped_elevation.tif
clipped_elevation.png
```

The resulting `clipped_elevation.tif` can then be opened directly in GIS software.

## Coordinate Reference System

For correct results, the vector and raster should use compatible coordinate reference systems (CRS).

If the vector and raster use different CRS definitions, the vector should be reprojected to the raster's CRS before clipping.

## Use Cases

This tool can be useful for:

* Remote sensing workflows
* Land-use and land-cover analysis
* Digital elevation model (DEM) clipping
* Satellite imagery preprocessing
* Administrative boundary extraction
* Watershed analysis
* GIS data preparation
* Geospatial automation

## Project Structure

A recommended repository structure is:

```text
raster-clipper/
│
├── raster_clipper.py
├── requirements.txt
├── README.md
├── LICENSE
└── .gitignore
```

## License

This project is open source. Add the appropriate license file to the repository before publishing if you intend to specify reuse and distribution terms.

## Author

Developed as a Python-based geospatial raster processing utility.

If you find this project useful, feel free to ⭐ the repository.
