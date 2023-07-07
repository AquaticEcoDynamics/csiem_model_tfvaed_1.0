## Cockburn Sound model : meteorological (BARRA) boundary condition files 

<br>

This folder contains the outputs from the BARRA weather reanalysis dataset, processed for use by the TUFLOW-FV Cockburn Sound model. For more information about this data set please refer to the [Bureau of Meteorology's BARRA Reanalysis](https://aquaticecodynamics.github.io/csiem-science/) page.

The files include weather variables () specific to the CSIEM model domain.

Original BARRA outputs are available from :

https://dapds00.nci.org.au/thredds/catalog/cj37/BARRA/BARRA_PH/v1/forecast

Scripts for processing the BARRA outputs into a reduced NC file for TUFLOW-FV are available from:

https://gitlab.com/tuflow-user-group/tuflow-fv/data-pre-processing/get-atmos

Files in this folder include (Apr 2023):

```
BARRA_R_20130101_20140101.nc
BARRA_PH_20130101_20131231.nc
BARRA_PH_20150101_20151231.nc
```

Note that two resolutions are available and processed:

 - BARRA_R (12km resolution over Australia, New-Zealand and the maritime continent) for the period 1990-01-01 to 2019-02-28
 - BARRA_PH (1.5km resolution over South-West WA) for the period 1990-01-01 to 2019-02-28

These files are not stored in GitHub and can be accessed from the CSIEM model archive on Pawsey:

```
wamsi: wamsi-westport-project-1/tfvaed/bc_repo
```

For more information on the CSIEM model setup, please visit the model documentation [here](https://aquaticecodynamics.github.io/csiem-science/) (note: currently under development).