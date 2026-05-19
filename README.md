# GIS-R-Tutorial

Two tutorials on working with spatial data in R for political science research, by [Tuğba Bozçağa](https://www.tugbabozcaga.com).

## Tutorials

### 1. GIS Visualization and Analysis in R (`GIS_Workshop.Rmd`)

An introduction to geospatial data and analysis in R. Originally designed for the MIT Political Science Methods Workshop series (Spring 2018, Spring 2019) and updated to use the modern `sf` and `terra` stack.

Topics:

- Spatial data structures (points, polygons, coordinate reference systems)
- Importing and exporting spatial data
- Combining spatial data with non-spatial sources (attribute and spatial joins)
- Mapping with base R, `ggplot2` (`geom_sf`), and `tmap`
- Geocoding and distance calculations
- Detecting spatial autocorrelation (Moran's I) and spatial regression (SAR, SEM)

A hosted version of the original 2019 tutorial is available on [RPubs](https://rpubs.com/bozcaga/GIS-in-R).

### 2. Quasi-Experimental Designs Using Spatial Data (`Quasi_Experimental_Designs_Spatial_Data.Rmd`)

A second tutorial on using spatial data for causal identification, taught at the Mannheim Political Methodology Summer School.

Topics:

- Spatial autocorrelation as a SUTVA violation
- Spatial confounding
- Geographic regression discontinuity (GRD)
- Difference-in-differences with spatially assigned treatment (with donut and ring specifications)
- Matching on spatial covariates
- Spatial regression (SAR, SEM) as a robustness diagnostic

The tutorial is self-contained: it builds a simulated study region so no external data is required.

## Data

The `data/BostonData/` folder contains the shapefiles and CSVs used by `GIS_Workshop.Rmd`:

- `city_council_districts.shp` (Boston city council districts)
- `Boston_N.shp` (Boston neighborhoods with demographic variables)
- `dist_results.csv` (election results)
- `graffiti.csv` (municipal service requests for graffiti removal)

## Running the tutorials

Clone the repo, open the `.Rmd` in RStudio, and click **Knit**. Required packages:

```r
install.packages(c(
  "sf", "terra", "tidyverse", "tmap", "spdep", "spatialreg",
  "tidygeocoder", "ggmap", "RColorBrewer", "units", "knitr",
  "fixest", "MatchIt", "rdrobust", "broom"
))
```

Some chunks in `GIS_Workshop.Rmd` use online basemaps that require API keys (Stadia Maps, Google Maps); these chunks are marked `eval = FALSE` and the keys should be set in `~/.Renviron` rather than hard-coded. See the tutorial text for details.

## License

The tutorial text and code are released under CC-BY 4.0; please cite if you reuse.
