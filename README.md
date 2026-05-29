# Sackville River Watershed: Mapping Land Cover and Urban Pressure

> A GIS portfolio project examining land cover and development pressure
> in the Sackville River watershed, Halifax Regional Municipality.

**Author:** Vinura Jayowin Amarasinghe
**Status:** In progress
**Tools:** QGIS (Long Term Release 3.40+)

---

## The question

The Sackville River drains from rural, forested headwaters near Beaver
Bank, through the rapidly urbanizing Sackville–Bedford corridor, and
into Bedford Basin and ultimately Halifax Harbour. What does the
watershed actually look like in terms of land cover, and where is
urban development pressure concentrated relative to the river network?

## Why it matters

Urbanizing watersheds in Atlantic Canada are subject to well-documented
pressures: stormwater runoff, road-salt loading, sediment from
construction, and loss of riparian buffer. The Sackville River has been
the focus of long-running restoration efforts by the Sackville Rivers
Association and others. A clear visual picture of where the watershed is
forested, where it is urbanized, and where these zones meet the river
network is a useful starting point for any environmental assessment or
restoration planning.

## What's in this repo

- `qgis/` — QGIS project file(s) and styling files
- `data/raw/` — original downloaded data (gitignored; see Data section to reproduce)
- `data/processed/` — clipped and reprojected layers used in the maps (gitignored)
- `maps/` — final exported maps (PNG and PDF)
- `notes/` — working notes on data sources and methodology

## Data sources

| Layer | Source | Format |
|---|---|---|
| Watershed boundaries | Nova Scotia GeoNova | Shapefile |
| Land cover (NS Topographic Database) | data.novascotia.ca | Shapefile / GeoJSON |
| Hydrographic features (rivers, lakes) | Nova Scotia GeoNova | Shapefile |
| HRM municipal boundary | Halifax Open Data Hub | Shapefile / GeoJSON |

Specific download URLs and version dates are recorded in `notes/data_sources.md`.

## The maps

1. **Overview / locator** — Sackville watershed boundary in the context of HRM, with the river network and major lakes
2. **Land cover classification** — current land cover within the watershed, classified into forest, urban, wetland, water, agriculture, and other
3. **Urban pressure** — overlay of urban land cover proximity to the river network, highlighting where development pressure meets the stream

## Methods

- All layers reprojected to **NAD83 / UTM Zone 20N (EPSG:26920)** for consistent measurement
- Watershed boundary used as the analytical clip mask for all other layers
- Land cover summarized by area within the watershed (km² and %)
- Urban-proximity analysis: 100 m buffer around the river network intersected with urban land cover classes
- Map layouts produced in QGIS Print Layout, exported at 300 DPI

## Reproduce the maps

```bash
# Clone the repo
git clone https://github.com/vinura-amarasinghe/sackville-watershed-mapping.git
cd sackville-watershed-mapping
```

Then:

1. Download the source layers from the URLs in `notes/data_sources.md` into `data/raw/`
2. Open `qgis/sackville_watershed.qgz` in QGIS 3.40 or later
3. Re-run the processing steps documented in `notes/methods.md`
4. Export maps from QGIS Print Layout

## Key findings

- The Sackville River watershed covers approximately 150 km² north of Bedford Basin, HRM
- Forest cover dominates the upper watershed (Beaver Bank / Upper Sackville headwaters)
- **36% of the 100m riparian buffer is unforested**, indicating significant urban pressure on the stream network
- Unforested riparian zones are concentrated in the lower watershed — the Bedford / Lower Sackville corridor — reflecting the historical urbanization gradient from rural headwaters to the suburban fringe at Bedford Basin
- Analysis used a 100m buffer around the stream network intersected with NS Topographic Database land cover (forest polygons), with the unforested remainder representing potential pressure zones

## License

Code and methodology: MIT (see `LICENSE`).
Data: governed by the respective licenses of the source organizations
(Government of Nova Scotia Open Information Licence; HRM Open Data License).