# particle-analysis
The repository contains geospatial analyses scripts to show the local relationships and dependencies of particulate matter measurement
data with semivariances. 
Also, temporal relationships as season or weekly-dependent differences are analyzed here.

## How to run

To explore kriging and the analyses, first run a jupyter notebook.

```
jupyter notebook
```

Then the kriging process can be explored

```
get_raw_data >> distance_matrix >> variogram_cloud >> empirical_variogram >> semivariogram
[grid, get_raw_data, distance_matrix, semivariogram] >> kriging >> result
```

in the `analysis.ipynb` with the parameters `start-time [UTC]` (time for analysis), `bounding-box [geojson-like]` (spatial bounding box), `distance-bins [m]` (size of distance bins), `max-range [UTC]` (maximum distance for PM correlation in kriging) and `target-grid [m]` (calculation grid size). 

When different parameters (e.g. time ranges) are analysed, also the differences between the dependencies (semivariances) can be explored with statistical significance tests in `statistical_test.ipynb`.

### Alternative

Alternatively, you can run and parametrize both notebooks with [papermill](https://github.com/nteract/papermill).

`analysis.ipynb`:

```
papermill analysis.ipynb analysis_<start-time>_<bounding-box>_<distance-bins>_<max-range>.ipynb -p START_TIME <start-time> -p BOUNDING_BOX <bounding-box> -p DISTANCE_BINS <distance-bins> -p MAX_RANGE <max-range> -p TARGET_GRID <target-grid>
```

`statistical_test.ipynb`:

```
papermill statistical_test.ipynb statistical_test_<start-time1>_<bounding-box1>_<distance-bins1>_<max-range1>_<start-time2>_<bounding-box2>_<distance-bins2>_<max-range2>.ipynb -p START_TIME1 <start-time1> -p BOUNDING_BOX1 <bounding-box1> -p DISTANCE_BINS1 <distance-bins1> -p MAX_RANGE1 <max-range1> -p START_TIME2 <start-time2> -p BOUNDING_BOX2 <bounding-box2> -p DISTANCE_BINS2 <distance-bins2> -p MAX_RANGE2 <max-range2>
```
