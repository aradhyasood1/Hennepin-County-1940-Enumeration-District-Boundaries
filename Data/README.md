# Boundary files and project versions

These are the enumeration district boundary inputs used by the Historical Covenants Project. Each shapefile consists of `.shp`, `.shx`, `.dbf` and `.prj` components; download all four together.

| Census year / version | File | Features | Coordinate reference system |
|---|---|---:|---|
| 1910 | [ED_1910_Suburbs_v6.shp](1910/ED_1910_Suburbs_v6.shp) | 221 | NAD83 / UTM zone 15N, EPSG:26915 |
| 1920 | [ED_1920_Suburbs_v4.shp](1920/ED_1920_Suburbs_v4.shp) | 271 | NAD83 / UTM zone 15N, EPSG:26915 |
| 1930 | [ED_1930_Suburbs_v4.shp](1930/ED_1930_Suburbs_v4.shp) | 326 | NAD83 / UTM zone 15N, EPSG:26915 |
| 1940, original county layer | [ED_1940_Hennepin_v9.shp](ED_1940_Hennepin_v9.shp) | 525 | NAD83 / UTM zone 15N, EPSG:26915 |
| 1940, project analysis layer | [enumdist_corrected.shp](1940_analysis/enumdist_corrected.shp) | 482 | WGS 84, EPSG:4326 |

## Sources

The original cartographic sources are U.S. Census Bureau enumeration district maps held by the National Archives. The [1900–1940 collection, microfilm publication A3378](https://www.archives.gov/research/census/1930/enumeration-districts-maps.html), is arranged by state, county, census year and local jurisdiction. The [repository README](../README.md) gives the six National Archives catalogue links for the 1940 maps and the dataset citation.

The earlier-year layers were prepared for the Historical Covenants Project. Their original project filenames, attributes, coordinate systems and geometries are retained in this release. `ED_int` identifies districts within each census year. Analysis across census years uses spatial crosswalks.

## The two 1940 versions

The original public county layer is byte-for-byte identical to the project's `ED_1940_Suburbs_v9` files for all four core components. The index is provided under the conventional filename `ED_1940_Hennepin_v9.shx`; the existing filename containing a space is retained.

`enumdist_corrected` is the project's 1940 analysis layer used in address matching and migration-instrument crosswalks. It has a smaller geographic extent and 482 districts whose identifiers also occur in the 525-district county layer. Its geometries differ from the county layer after putting both in the same coordinate system. Use the version named by the analysis being replicated.

## Integrity

[replication_manifest.json](replication_manifest.json) records feature counts, coordinate systems, field definitions, original project paths and SHA-256 checksums. All added shapefile components were compared byte-for-byte with the project inputs and each shapefile was reopened after copying. Layers contain district boundaries, identifiers and working notes.
