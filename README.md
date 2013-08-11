kaggle_solarenergy
==================

AMS 2013-2014 Solar Energy Prediction Contest

https://www.kaggle.com/c/ams-2014-solar-energy-prediction-contest/data


The contest training data are separated into 3 files.

gefs_train.tar.gz and gefs_train.zip contain all of the GEFS training data. The data are in netCDF4 files with each file holding the grids for each ensemble member at every time step for a particular variable. Each netCDF file contains the latitude-longitude grid and timestep values as well as metadata listing the full names of each variable and the associated units. More infromation about the netCDF format and links to open libraries for reading the files can be found here. NetCDF libraries are known to be available for C, Java, Python, R, and MATLAB.

Each netCDF4 file contains the total data for one of the model variables and are stored in a multidimensional array. The first dimension is the date of the model run and will correspond directly with a row in either the train.csv or sampleSubmission.csv files. The second dimension is the ensemble member that the forecast comes from. The GEFS has 11 ensemble members with perturbed initial conditions. The third dimension is the forecast hour, which runs from 12 to 24 hours in 3 hour increments. All model runs start at 00 UTC, so they will always correspond to the same universal time although local solar time will vary over each year.  The fourth and fifth dimensions are the latitude and longitude uniform spatial grid. The longitudes in the file are in positive degrees from the Prime Meridian, so subtracting 360 from them will translate them to a similar range of values as in station_info.csv. A visualization of the grid can be seen on the main page.

Variable  Description	Units
apcp_sfc	3-Hour accumulated precipitation at the surface	kg m-2
dlwrf_sfc	Downward long-wave radiative flux average at the surface	W m-2
dswrf_sfc	Downward short-wave radiative flux average at the surface	W m-2
pres_msl	Air pressure at mean sea level	Pa
pwat_eatm	Precipitable Water over the entire depth of the atmosphere	kg m-2
spfh_2m	Specific Humidity at 2 m above ground	kg kg-1
tcdc_eatm	Total cloud cover over the entire depth of the atmosphere	 %
tcolc_eatm	Total column-integrated condensate over the entire atmos.	kg m-2
tmax_2m	 Maximum Temperature over the past 3 hours at 2 m above the ground	 K
tmin_2m	 Mininmum Temperature over the past 3 hours at 2 m above the ground	 K
tmp_2m	 Current temperature at 2 m above the ground	 K
tmp_sfc	 Temperature of the surface	 K
ulwrf_sfc	 Upward long-wave radiation at the surface	 W m-2
ulwrf_tatm	 Upward long-wave radiation at the top of the atmosphere	 W m-2
uswrf_sfc	 Upward short-wave radiation at the surface	 W m-2
train.csv contains the total daily incoming solar energy in (J m-2) at 98 Oklahoma Mesonet sites that have been in continuous operation since January 1, 1994. The solar energy was directly measured by a pyranometer at each Mesonet site every 5 minutes and summed from sunrise to 23:55 UTC of the date listed in each column.

station_info.csv contains the latitude, longitudes, and elevation (meters) of each Mesonet station.
