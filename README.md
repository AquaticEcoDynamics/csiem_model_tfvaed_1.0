<a name="readme-top"></a>

<!--
Readme for the tfvaed_1.0 Cycle 1 Cockburn Sound model
-->

<!-- PROJECT SHIELDS -->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">

<!--
  <a href="https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>
-->

<h3 align="center">WAMSI Westport <em>Cockburn Sound Water Quality Model</em></h3>

  <p align="center">
    This repository houses the hydrodynamic-biogeochemical model for Cockburn Sound, a coastal embayment located near Perth, Western Australia.
    <br />
    <a href="https://aquaticecodynamics.github.io/csiem-science/"><strong>Explore the online manual »</strong></a>
    <br />
    <br />
    <a href="https://aquaticecodynamics.github.io/csiem-science/appendix-b-results-archive.html">View Demo</a>
    ·
    <a href="https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/issues">Report Bug</a>
    ·
    <a href="https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

<br>

<!-- ABOUT THE PROJECT -->

## About The Project

<!-- [![Product Name Screen Shot][product-screenshot]](https://example.com) -->
<br>

In 2022, the Western Australian Marine Science Insitution and Wesport commisioned development of an independent hydrodynamic-biogeochemical model for [Cockburn Sound](https://en.wikipedia.org/wiki/Cockburn_Sound), which is located on the coast of Perth, Western Australia.

The model uses the [TUFLOW-FV](https://www.tuflow.com/products/tuflow-fv/) 3D finite volume hydrodynamic model, and the [AED](https://aquaticecodynamics.github.io/aed-science/) water quality model.

<!-- Do a search and replace with your text editor for the following: `github_username`, `repo_name`, `twitter_handle`, `linkedin_username`, `email_client`, `email`, `project_title`, `project_description` -->

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Built With

<br>

[![TUFLOW-FV](https://img.shields.io/badge/TUFLOW--FV-2023.0.0-yellow)](https://tuflow.com/products/tuflow-fv/)
[![AED](https://img.shields.io/badge/AED-2.2.4-brightgreen)](https://aquatic.science.uwa.edu.au/research/models/AED/quickstart.html)

<!--
* [![Next][Next.js]][Next-url]
* [![React][React.js]][React-url]
* [![Vue][Vue.js]][Vue-url]
* [![Angular][Angular.io]][Angular-url]
* [![Svelte][Svelte.dev]][Svelte-url]
* [![Laravel][Laravel.com]][Laravel-url]
* [![Bootstrap][Bootstrap.com]][Bootstrap-url]
* [![JQuery][JQuery.com]][JQuery-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>
-->
<br>

<!-- GETTING STARTED -->

## Getting Started

<br>

This repository contains model files (except the `bc_repo`) that are version-controlled can be run locally on Windows or Linux. The `bc_repo` contains boundary conditions files that the sizes are too large to be stored at Github, 
therefore they are stored on Pawsey WAMSI project folder and can be accessed by direct download or a `fetch` method (see below). To get a local copy up and running follow these steps.

### Prerequisites

Running the model contained herein requires users to have an active TUFLOW-FV binary and license with the AED pre-compiled plugin.

- Download and install the TUFLOW-FV model and license server from [WBM BMT](https://www.tuflow.com/products/tuflow-fv/).

- Download and install the compatible AED model plugin (FV-AED) from [the UWA-AED website](https://aquatic.science.uwa.edu.au/research/models/AED/quickstart.html).

### Cloning and executing the model

1. Clone the current csiem_model_tfvaed_1.0 repo
   ```sh
   Linux: git clone https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0.git
   Windows: use Github Destop to clone or download ZIP at the Github website
   ```
2. Clone the complete model files including `bc_repo` folder. For Linux users, copy the fetch_csiem.sh shell file from the Github [csiem_model_tools](https://github.com/AquaticEcoDynamics/csiem_model_tools/blob/main/fetch/fetch_csiem.sh) repository. Then fetch the `bc_repo` as:
   ```sh
   ./fetch_csiem.sh 1.0
   ```
   The above fetch command will download all the model files including the bc_repo;
   
3. Go to the main model run directory, and execute model as:
   ```sh
   {tfv_aed binary} {csiem model tfvaed 1.0 main configuration}.fvc
   ```

### Folder structure and file naming conventions

1. Folder structure: model files are organized in the following catogories/folders:

| Folders        | Content                                                     |
| -------------- | ----------------------------------------------------------- |
| **bc_repo**    | repository for boundary condition files                     |
| **gis_repo**   | repository for GIS files required by the model simulations  |
| **includes**   | model configuration files for being included in simulations |
| **model_runs** | main model configuration files                              |
| **outputs**    | place holder for model output storage                       |

2. File naming convention: model files are named using the following conventions:

- model_runs

| Sub-type                | Conventions                                                            | comments                                                                                                                                                                                          |
| ----------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| WQ (water quality)      | csiem\_{model generation ID}\_{mesh option}\_{model period}\_WQ.fvc    | Main configuration file for coupled TFV-AED model, e.g. csiem_v1_B009_20130101_20131231_WQ.fvc                                                                                                    |
| HD (hydrodynamics)      | csiem\_{model generation ID}\_{mesh  option}\_{model  period}\_HD.fvc  | Main configuration file for TFV hydrodynamic model only, e.g. csiem_v1_B009_20130101_20131231_HD.fvc                                                                                              |
| ST (sediment transport) | csiem\_{model generation ID}\_{mesh  option}\_{model  period}\_SED.fvc | Main configuration file for TFV-ST model, e.g. csiem_v1_B009_20130101_20131231_ST.fvc.<br> Note: the TFV-ST model was originally set by BMT and to be updated with corresponding file paths/names |

- includes

| Sub-type                 | Conventions                                       | comments                                                                         |
| ------------------------ | ------------------------------------------------- | -------------------------------------------------------------------------------- |
| bc (boundary conditions) | {boundary type}\_{data source}\_{data period}.fvc | e.g. met_BARRA_perth_20130101_20131231.fvc                                       |
| ic (initial condition)   | initial_conditions\_{model version}.fvc           | e.g. initial_conditions_wq.fvc                                                   |
| domain                   | domain_config\_{mesh option}\_{model type}.fvc    | e.g. domain_config_csiem_mesh_B.fvc                                              |
| turbulence               | turbulence.fvc                                    | Include configuration for turbulence parameters                                  |
| wq (water quality)       | AED model configuration files                     | Include configuration for AED water quality module                               |
| output                   | output\_{output category}.fvc                     | Configuration for model outputs, e.g. output_wq.fvc                              |
| roughness                | roughness_material\_{version NO}.fvc              | Configuration for benthic roughness settings, e.g. roughness_wq_Material_011.fvc |

- bc_repo

| Sub-type                                 | Conventions                                                                                              | comments                                                                             |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| 1_ocean (ocean boundary)                 | - NetCDF: {data source}\_{UTC zone}\_{data period}.nc <br> - CSV: ocean_bgc\_{source}\_{data period}.csv | e.g. ROMS_UTC+8_20130101_20140101_FILLED.nc<br> ocean_bgc_IMOS_20220101_20221231.csv |
| 2_weather (weather condition)            | {data source}\_{domain}\_{UTC zone}\_{data period}.nc                                                    | e.g. WRF_d02_UTC+0_20220101_20230101.nc                                              |
| 3_waves (waves inputs)                   | {data source}\_{domain}\_{UTC zone}\_{data period}.nc                                                    | e.g. WWM_Agrid_UTC+0_20150101_20151231.nc                                            |
| 4_sce (Swan-Canning Estuary)             | {location}\_{BC type}\_{ data period}\_{model type}.csv                                                  | e.g. NAR_Inflow_20100101_20230101_wq.csv                                             |
| 5_phe (Peel-Harvey Estuary)              | N/A (to be updated)                                                                                      |                                                                                      |
| 6_gw (Groundwater inputs)                | SGD\_{zone id}\_{data period}.csv                                                                        | e.g. SGD_zone1_1_20130101_20131231.csv                                               |
| 7_discharges (industrial discharge)      | {data source}\_{data period}.nc                                                                          | e.g. BP_20130101_20140101_wq.csv                                                     |
| 8_intakes (industrial intakes)           | {data source}\_{data period}.nc                                                                          | e.g. PSDP1_20130101_20140101_wq.csv                                                  |
| 9_operations (Cockburn Sound operations) | N/A (to be updated)                                                                                      |                                                                                      |

- gis_repo

| Sub-type                                         | Conventions                                         | comments                             |
| ------------------------------------------------ | --------------------------------------------------- | ------------------------------------ |
| 1_domain (GIS files for model domain)            | csiem\_mesh\_{mesh option}\_{version ID}\_{resolution} | e.g. csiem_mesh_B009_opt.2dm         |
| 2_benthic (GIS files for benthic conditions)     | csiem\_{benthic type}\_{version ID}                   | e.g. Cockburn_Sound_Material_011.shp |
| 3_output (GIS files for output definition)       | extraction_point.csv                                |                                      |
| 4_gw (GIS files for defining groundwater inputs) | groundwater\_zones\_{version NO}                      | e.g. groundwater_zones_v2.shp        |

### Analysis

Input files and model output files are able to be processed using the `csiem-marvl` repository that includes the supporting scripts and site data. Please contact the developers for further information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->

<!--
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>
-->

<!-- ROADMAP -->

<!--
## Roadmap

- [ ] Feature 1
- [ ] Feature 2
- [ ] Feature 3
    - [ ] Nested Feature

See the [open issues](https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>
-->

<!-- CONTRIBUTING -->

## Contributing

Contributions from the user and developer community are welcome and **greatly appreciated**!.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->

## License

Distributed under the --- License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTACT -->

## Contact

Matt Hipsey: [@matthipsey](https://twitter.com/matthipsey) - matt.hipsey@uwa.edu.au

Project Link: [csiem online manual](https://aquaticecodynamics.github.io/csiem-science/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ACKNOWLEDGMENTS -->

## Acknowledgments

- Funding from the [WAMSI Westport Research Program](https://wamsi.org.au/research/programs/wamsi-westport-marine-science-program/)
- Gayan Gunaratne, Louise Bruce and the [BMT](https://www.tuflow.com/) software team
- Brendan Busch & Peisheng Huang from the [AED](https://aed.see.uwa.edu.au/) research group
- Oceanographic models from Ivica Janeković & Chari Pattiaratchi from the [UWA Oceans Institute](https://www.uwa.edu.au/oceans-institute)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/AquaticEcoDynamics/csiem_model_tfvaed_1.0.svg?style=for-the-badge
[contributors-url]: https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/AquaticEcoDynamics/csiem_model_tfvaed_1.0.svg?style=for-the-badge
[forks-url]: https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/network/members
[stars-shield]: https://img.shields.io/github/stars/AquaticEcoDynamics/csiem_model_tfvaed_1.0.svg?style=for-the-badge
[stars-url]: https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/stargazers
[issues-shield]: https://img.shields.io/github/issues/AquaticEcoDynamics/csiem_model_tfvaed_1.0.svg?style=for-the-badge
[issues-url]: https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/issues
[license-shield]: https://img.shields.io/github/license/AquaticEcoDynamics/csiem_model_tfvaed_1.0.svg?style=for-the-badge
[license-url]: https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/linkedin_username
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com
