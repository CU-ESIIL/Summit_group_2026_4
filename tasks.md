Geospatial Harmonization Tasks
This document describes the steps needed to harmonize multiple geospatial datasets so they can be directly compared or analyzed together. It is tool-agnostic — the same pipeline applies whether you use command-line utilities, Python, R, or any other stack.

Input
One or more dataset URLs (raster or vector)
A target region of interest (state, county, custom boundary, or bounding box)
A target coordinate reference system (CRS)
A target spatial resolution
Task 1: Validate Data Sources
Check that every dataset URL is reachable and returns actual geospatial data (not an HTML portal page or a login screen). If a URL fails, stop and report which one failed before doing anything else.

Task 2: Download Datasets
Download each dataset from its URL. If a file is a compressed archive (ZIP), extract it. Identify the geospatial file inside each archive — look for GeoTIFF, Shapefile, GeoJSON, GeoPackage, or NetCDF files.

Task 3: Determine the Target Grid
Resolve the region of interest to a bounding box and, when available, an actual boundary polygon.

For US states, counties, or places, look up the boundary from an authoritative source (e.g. Census TIGER boundaries).
For international or custom regions, ask the user for a boundary file or a bounding box in the target CRS.
Choose an appropriate CRS: geographic (e.g. EPSG:4326) for broad areas, projected (e.g. a UTM zone) for local analysis that needs accurate distances.
Task 4: Reproject to a Common CRS
Transform every dataset — both rasters and vectors — into the target coordinate reference system so they all share the same spatial reference.

Task 5: Clip to the Region of Interest
Crop all datasets to the target area.

If a boundary polygon is available, clip to the actual boundary shape (not just the rectangular bounding box). This avoids including data from neighboring regions.
If only a bounding box is available, clip to that rectangle.
Task 6: Resample Rasters to a Common Resolution
Bring all raster datasets to the same pixel size.

Use nearest-neighbor resampling for categorical data (land cover classes, fuel model codes, soil types) — interpolating between class codes produces meaningless values.
Use bilinear interpolation for continuous data (temperature, precipitation, elevation) — this preserves smooth gradients.
If you are unsure which method to use for a dataset, ask the user.
Task 7: Handle Vector Data
For each vector dataset, decide whether to:

Keep it as a vector — reproject and clip to the target area, save as GeoJSON. Good when you need the original geometry (fire perimeters, administrative boundaries).
Rasterize it to the target grid — convert to a raster at the target resolution by burning a constant value (e.g. 1 = present, 0 = absent). Good for large point or polygon datasets (building footprints, road networks) that need to align with raster layers.
Task 8: Save Harmonized Outputs
Save each harmonized dataset:

Rasters → GeoTIFF (.tif)
Vectors → GeoJSON (.geojson)
All outputs should share the same CRS, extent, and (for rasters) resolution.

Task 9: Generate Visualization
Create a multi-panel map showing all harmonized layers side by side, saved as a PNG image. This gives a quick visual check that everything aligned correctly.

Task 10: Document the Work
Record what was done so the analysis is reproducible:

The original user request
Which datasets were used (URLs)
Key decisions made (CRS, resolution, resampling method, rasterize vs. keep vector)
Any issues encountered and how they were resolved
