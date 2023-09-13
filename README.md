# AI methods for data processing

### ENRICH Sensor Marketplace

Collaboration of experience and expertise relating to AI methods for data processing.

### Problem Statement

Researchers across the four institutes (4RI) make extensive use of **spatial** and **timeseries** datasets. These datasets are often from imperfect sensors and may contain gaps, anolomolies, require transformation or suffer from lack of resolution. Significant project time is invested in developing methods and tools for cleaning and preparing these imperfect datasets for further analysis. In the last years machine learning methods have become a key tool for data processing tasks however their uptake and appropriate usage across the 4RI's has been limited to date.

This repository attempts to collate relevent tools and projects from across the 4RI as a first step in promoting collaboration in developing common tools and expertise in data processing.

## Projects

Below follows a selection of projects and tools which have been used to address the problem statement. 

|                       | Spatial | Timeseries         |
| --------------------- | ------- | ------------------ |
| **Gap Filling**       | DINEOF  |                    |
| **Anomoly Detection** |         | ADAsen <br> ENVASS |
| **Resolution**        |         |                    |
| **Transformation**    |         | bulk2skin          |

Summary table of projects described below.

### ADAsen

@Andreas please can you complete this sections

As part of the ADAsen project an interactive annotation tool for labelling time series and 2D data was developed.

Russo, S. (2020). ADASen Labelling Tool (Version 1.0). Eawag: Swiss Federal Institute of Aquatic Science and Technology. https://doi.org/10.25678/0002PC

### ENVASS

ENVironmental data quality ASSurance

ENVASS is an attempt to standardise some basic quality assurance (QA) methods for timeseries data. This was developed to ensure consistency in QA between the processing pipelines of heterogeneous in-situ data sources collected by the Eawag SURF department.

https://github.com/eawag-surface-waters-research/envass ||
https://pypi.org/project/envass/

| Name           | Institute | Email                   |
| -------------- | --------- | ----------------------- |
| James Runnalls | Eawag     | james.runnalls@eawag.ch |

### bulk2skin

It is known that the lake skin temperature readings between satellite imagery and in-situ lake surface temperature (at about 1cm depth) can have temperature differences of more than 2°C during a regular day. This divergence is due to an undetermined function of heat transfer between the lake and the atmosphere.

In order solve this undertermined function, we use machine learning to find a data-driven mapping function between temperature simulations at 1m depth (bulk temperature) and lake skin temperature. Since the disparity between skin and bulk temperature arises from turbulence and heat transfer near the water surface, we hypothesize that a mapping from a bulk temperature to skin temperature would be a function of additional meteorological components. For this purpose, we rely on auxiliary features such as wind velocity, air temperature, humidity, and solar irradiance, which can be obtained either for specific in-situ meteo-stations or over a whole lake through MeteoSwiss probabilistic estimates. Accordingly, we optimize a deep learning model with long short-term memory (LSTM) architecture that not only utilizes a set of features, but also exploits temporal patterns for learning an accurate mapping to the lake skin temperature. Our results on separate test evaluations show that albeit extreme sparsity within sensory data, our model can significantly improve lake skin temperature estimations compared to solely relying on bulk temperature.

An important aspect when modeling this mapping function is to retain the Bayesian nature for predicted values of the lake surface temperature, that is, to provide an estimate of uncertainty. We combine multiple methodologies from the literature [Kendall’17, Tagasovska’19, Tagasovska’21] to quantify uncertainties for model predictions based on different sources. Consequently, we can adjust the influence of a given satellite imagery on the likelihood of hydrological model simulation particles.

https://gitlab.renkulab.io/firat.ozdemir/bulk2skin-estimates

| Name          | Institute | Email                      |
| ------------- | --------- | -------------------------- |
| Firat Ozdemir | SDSC      | firat.ozdemir@sdsc.ethz.ch |
| Artur Safin   | Eawag     | artur.safin@eawag.ch       |

### DINEOF

DINEOF is an EOF-based method to fill in missing data from geophysical fields, such as clouds in sea surface temperature.

https://github.com/aida-alvera/DINEOF

It has been used in the LakeCREST project for spatial gap filling of remote sensing images.

https://gitlab.renkulab.io/eawagrs/lakecrest

| Name                | Institute | Email                         |
| ------------------- | --------- | ----------------------------- |
| Elisa Calamita      | Eawag     | elisa.calamita@eawag.ch       |
| Michael Brechbühler | Eawag     | michael.brechbuehler@eawag.ch |

## Group Members

| Name            | Institute | Email                     |
| --------------- | --------- | ------------------------- |
| Erik Froejdh    | PSI       | erik.froejdh@psi.ch       |
| Andreas Frömelt | Eawag     | andreas.froemelt@eawag.ch |
| Matthias Haeni  | WSL       | mathias.haeni@wsl.ch      |
| Mirko Lukovic   | WSL       | mirko.lukovic@wsl.ch      |
| James Runnalls  | Eawag     | james.runnalls@eawag.ch   |
| Jan Svoboda     | SLF       | jan.svoboda@slf.ch        |
| Roman Zweifel   | WSL       | roman.zweifel@wsl.ch      |
