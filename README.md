# Croplandmaps_V2 - Vector tiles

Renders cropland maps as vector tiles to improve performance. Tiles only load the data a user needs at their current view and zoom level, which means they need to download less data and that data renders faster.

Some compromises are made when converting to tiles, to keep the tiles below a reasonable size. Some small features are removed or simplified at low zoom levels. These settings can be adjusted in the `./scripts/process` file (see the "Generating vector tiles" section for how to reprocess the tiles).

## Viewing the app

- Run a simple server such as `python3 -m http.server`

## Generating tiles

This project contains pregenerated tiles, which might be all you need. But if you want to change the tile generation settings, you can rerun the process.

### Install dependencies

- Tippecanoe: [installation instructions](https://github.com/mapbox/tippecanoe#installation)
- MBUtil: [installation instructions](https://github.com/mapbox/mbutil#installation)

### Add data

- Add files `aoi1_boundarymerge.geojson` through `aoi16_boundarymerge.geojson` to `/data/input`

### Generating vector tiles

- Run the script `./scripts/process`
- Move `/data/_output/tiles` to the root directory to view in app
