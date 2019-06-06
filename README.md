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

in the `analysis.ipynb`.

When different parameters (e.g. time ranges) are analysed, also the differences between the dependencies (semivariances) can be explored with statistical significance tests in `statistical_test.ipynb`.
