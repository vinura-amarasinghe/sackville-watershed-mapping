# Data Sources

All four layers downloaded from the Government of Nova Scotia Open Data
portal (data.novascotia.ca), 2026-05-28. Province-wide layers will be
clipped to the Sackville watershed in QGIS.

## 1. Watershed boundaries

- **Source:** Government of Nova Scotia — 1:10,000 Nova Scotia Sub-Tertiary Watersheds
- **Dataset page:** https://data.novascotia.ca/datasets/s4r5-2srh
- **Download URL:** https://data.novascotia.ca/api/geospatial/s4r5-2srh?method=export&format=Shapefile
- **File downloaded:** watersheds.zip → ns_watersheds.shp (+ .shx, .dbf, .cpg, .prj)
- **Date downloaded:** 2026-05-28
- **CRS:** to be confirmed in QGIS (expected: WGS84 / EPSG:4326 from Socrata export)
- **Notes:** Sub-tertiary level is finer than secondary; appropriate scale
  for delineating individual river watersheds like the Sackville.

## 2a. Hydrographic features — Watercourses (lines)

- **Source:** Government of Nova Scotia — Nova Scotia Topographic DataBase, Water Features (Line Layer)
- **Dataset page:** https://data.novascotia.ca/datasets/fpca-jrmt
- **Download URL:** https://data.novascotia.ca/api/geospatial/fpca-jrmt?method=export&format=Shapefile
- **File downloaded:** water_lines.zip → ns_water_lines.shp (+ .shx, .dbf, .cpg, .prj)
- **Date downloaded:** 2026-05-28
- **CRS:** to be confirmed in QGIS
- **Notes:** Rivers, streams, and other linear water features at 1:10,000 scale.

## 2b. Hydrographic features — Waterbodies (polygons)

- **Source:** Government of Nova Scotia — Nova Scotia Topographic DataBase, Water Features (Poly Layer)
- **Dataset page:** https://data.novascotia.ca/datasets/h8jb-hzrm
- **Download URL:** https://data.novascotia.ca/api/geospatial/h8jb-hzrm?method=export&format=Shapefile
- **File downloaded:** water_polys.zip → ns_water_polys.shp (+ .shx, .dbf, .cpg, .prj)
- **Date downloaded:** 2026-05-28
- **CRS:** to be confirmed in QGIS
- **Notes:** Lakes, ponds, reservoirs, swamps, and other polygon water features.

## 3. Land cover

- **Source:** Government of Nova Scotia — Nova Scotia Topographic Database, Land Cover (Poly)
- **Dataset page:** https://data.novascotia.ca/datasets/xed8-vvg5
- **Download URL:** https://data.novascotia.ca/api/geospatial/xed8-vvg5?method=export&format=Shapefile
- **File downloaded:** land_cover.zip → ns_land_cover.shp (+ .shx, .dbf, .cpg, .prj)
- **Date downloaded:** 2026-05-28
- **CRS:** to be confirmed in QGIS
- **Notes:** Polygon-based land cover from the NS Topographic Database at
  1:10,000 scale. Classes include forest types, agricultural land,
  urban/built-up, wetland, and water. Province-wide layer (~338 MB
  uncompressed); will be clipped to Sackville watershed in QGIS.

## 4. Municipal boundaries

- **Source:** Government of Nova Scotia — Municipality Boundaries
- **Dataset page:** https://data.novascotia.ca/datasets/7bqh-hssn
- **Download URL:** https://data.novascotia.ca/api/geospatial/7bqh-hssn?method=export&format=Shapefile
- **File downloaded:** municipalities.zip → ns_municipalities.shp (+ .shx, .dbf, .cpg, .prj)
- **Date downloaded:** 2026-05-28
- **CRS:** to be confirmed in QGIS
- **Notes:** All NS municipalities; will filter to HRM in QGIS.

---

## To-do after QGIS exploration

- Confirm and record CRS for each layer
- Note attribute fields used (e.g. watershed name field, land cover
  classification field)
- Document any data quality issues (gaps, slivers, classification
  inconsistencies) discovered during analysis