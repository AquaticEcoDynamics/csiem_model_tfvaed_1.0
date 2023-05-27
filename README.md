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

[![TUFLOW-FV](https://img.shields.io/badge/TUFLOW--FV-2020.008-yellow)](https://tuflow.com/products/tuflow-fv/)
[![AED](https://img.shields.io/badge/AED-2.0.5-brightgreen)](https://aquatic.science.uwa.edu.au/research/models/AED/quickstart.html)

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

This repository contains model files that can be run locally on Windows or Linux. To get a local copy up and running follow these steps.

### Prerequisites

This repository includes the model files required for a TUFLOW-FV - AED simulation run. Running the setup contained herein requires users to have an active TUFLOW-FV license with the AED [pre-compiled plugin](https://aquatic.science.uwa.edu.au/research/models/AED/quickstart.html).

Download and install the TUFLOW-FV model and license server.
* tuflow-fv
  ```sh
  ......
  ```
Download and install the compatible AED model plugin (FV-AED).
* fv-aed
  ```sh
  ......
  ```
### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/AquaticEcoDynamics/csiem_model_tfvaed_1.0.git
   ```
2. Fetch the dependent NetCDF files required as boundary conditions (BC's)
   ```sh
   ./fetch_csiem.sh 1.0
   ```
3. Enter the main model run directory, and execute model
   ```sh
   cd model_runs/ 
   /opt/bin/tfv_aed csiem_100_A_20130101_20130601_WQ_009.fvc
   ```

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

Project Link: [csiem_model](https://github.com/AquaticEcoDynamics/csiem_model)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* Funding from the [WAMSI Westport Research Program]()
* Gayan Gunaratne, Louise Bruce and the [BMT]() software team
* Brendan Busch & Peisheng Huang from the [AED]() research group
* Oceanographic models from Ivica Janeković & Chari Pattiaratchi from the [UWA Oceans Institute]()

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