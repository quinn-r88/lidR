R package for airborne LiDAR data manipulation and visualisation for forestry application

lidR package provides functions to read `.las` files, plot a cloud of points, compute metrics in an area-based approach, compute digital model of canopy, thin lidar data, automatically extract ground inventories, process a set of tiles on multicore, classify data from shapefiles and provides others tools to manipulate liDAR data. LidR is designed mainly for research purposes in an area-based approach.

lidR provides an open-source and R based implementation of the main functions from sofware like FUSION or lastools. lidR is flexible because it rely on the programmation of you own tools rather than the use of a set of given tools.

# Install lidR from Github with devtools

    install.package("devtools")
    devtools::install_github("Jean-Romain/lidR")
    library(lidR)
    
# Features 

- [Read .las files](http://jean-romain.github.io/lidR/loadLidar.html)
- [Retrieved indiviual pulses](http://jean-romain.github.io/lidR/loadLidar.html#dynamically-computed-fields)
- [Retrieve individual flightlines](http://jean-romain.github.io/lidR/loadLidar.html#dynamically-computed-fields)
- [Compute a digital model of canopy](http://jean-romain.github.io/lidR/lanopy.html)
- Compute any set of metrics on a cloud of point
- Rasterize and apply any function to compute a set of metrics in an area based approach
- Classify and filter data from geographic shapefiles
- Filter cloud of points based on any condition test
- Thin a cloud of point to reach an homogeneous point density
- Clip data base on disc, rectangle or polygon.
- Compute point and pulse densities
- Manage a catalog of `.las` tiles
- Extract automatically a set of ground plot inventories (even plot falling between two or more tiles)
- Analyse a full set a tiles in parallel computing
- [Plot 3D LiDAR data](http://jean-romain.github.io/lidR/plotLidar.html)
- plot in 2D and 3D the metrics
- Compute simple triangular irregular network (TIN)
    
# Some examples
     
## Plot data

	lidar = LoadLidar("myfile.las")
	plot(lidar)

![](https://github.com/Jean-Romain/lidR/blob/gh-pages/images/plot3d_1.jpg)

## Compute a simple metric

    metric = gridMetrics(lidar, 20, mean(Z))
    plot(metric)

![](https://github.com/Jean-Romain/lidR/blob/gh-pages/images/gridMetrics-mean.jpg)