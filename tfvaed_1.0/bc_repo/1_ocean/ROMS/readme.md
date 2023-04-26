## Cockburn Sound model : ocean boundary condition files (hydrodynamics)

<br>

This folder contains the outputs from the WA-ROMS hydrodynamics model developed as part of the WWMSP, processed for use by the TUFLOW-FV Cockburn Sound model. 

The files include water level and profiles of water velocty, salinity and temperature specific to the CSIEM model domain boundary.

Original model outputs from WA-ROMS are available from the Pawsey S3 storage:

```
wamsi: wamsi-westport-project-5
```

Scripts for processing the WA-ROMS outputs into a reduced NC file for TUFLOW-FV are available within this Github repo:

Files in this folder include (Apr 2023):

```
ROMS_UTC+8_20130101_20140101_FILLED.nc
ROMS_UTC+8_20150101_20160101_FILLED.nc
```

These files are not stored in GitHub and can be accessed from the CSIEM model archive on Pawsey:

```
wamsi: wamsi-westport-project-1/tfvaed/bc_repo
```

For more information on the CSIEM model setup, please visit the model documentation [here](https://aquaticecodynamics.github.io/csiem-science/) (note: currently under development).