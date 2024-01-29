# Croplandmaps - PMTiles

PMTiles Concepts

PMTiles is a single-file archive format for pyramids of tiled data. A PMTiles archive can be hosted on a storage platform like S3, and enables low-cost, zero-maintenance map applications.

Most of the process is referred to here: https://docs.protomaps.com/pmtiles/

Using the nature of PMTiles is a single-file archive format for pyramids of tiled data, each scaling level can be preloaded, which can solve the slow loading speed caused by vector files in .pbf format. The problem of large cache data.

## Web Map link

[PMTiles Openlayer Vector Web Map](https://grace-du.github.io/crop-land-maps/)

## Creating PMTiles


### Install dependencies

- Installed WSL (if your computer is Windows)
- Tippecanoe: [installation instructions](https://github.com/mapbox/tippecanoe#installation)
- MBUtil: [installation instructions](https://github.com/mapbox/mbutil#installation)
- Download the pmtiles binary for your system at go-pmtiles/Releases.

### Data processing
Convert the vector tiles to PMTiles format:

Combined GeoJSON Files:
```
sudo apt install jq
```
```
cat file1.geojson file2.geojson | jq -c '.features[]' | paste -sd "," - >> combined.geojson
```

Convert .geojson file to mbtiles:
```
tippecanoe -o output.mbtiles -Z min_zoom -z max_zoom input.geojson
```

Convert .mbtiles to .pmtiles:
```
pmtiles convert INPUT.mbtiles OUTPUT.pmtiles
```


### Generating Web Map

- Uploaded PMTiles to GitHub.https:main/congo.pmtiles
- Enabled GitHub Pages. Set GitHub page to [index.html](https://github.com/grace-du/crop-land-maps/blob/main/index.html)
