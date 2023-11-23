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

**Problem statement**

The current methods for sensor quality checking applied at Eawag, i.e. based on regular hardware inspection and a posteriori data inspection, are not adequate for use with the ever-larger data sets that are collected by researchers at Eawag. A new approach to sensor management is needed.

**Project goals**

The main goal of the project is **to increase the standard for online sensor management at Eawag** to a level that - as a bare minimum - includes the following elements:
 - Online sensor signals are checked automatically with simple algorithmic tools to identify basic issues as soon as they arise. These issues include presence of outliers, stuck or barely moving sensor signals, and out-of-range sensor values.
 - Online sensor signals are checked for important deviations from historical data (anomaly detection). Such deviations are caused by either (i) the presence of one or more sensor faults (fault detection) or (ii) meaningful changes in the monitored system (novelty detection). The use of such tools will decrease the time invested in sensor maintenance when the produced data appears normal (no fault & no novelty). Conversely, the time invested in sensor maintenance will be increased when the produced data is of low quality (faulty condition) or of large scientific value (novelty condition).
 - The research staff that manages the sensor signals will obtain automatic alerts of the presence of detected anomalies (faults or novelties) via e-mail, SMS, or other IT-based communication tools. As a result, they will be able to address sensor maintenance requirements exactly when it matters, i.e. shortly after the obtained sensor signals have turned faulty or when the collected data has turned extremely valuable.

**Deliverables**
- *Software*. Development of a software toolbox for online anomaly detection and anomaly visualization. A basic version will be ready and tested for Eawag-wide use by the end of the project.
- *Benchmarking*. The implemented tools for anomaly detection are benchmarked against each other to find out (i) what kind of algorithms are particularly useful for environmental system monitoring and (ii) whether or not state-of-the-art anomaly detection tools are sufficient to address the needs for such tools at Eawag.
- *Knowledge transfer*. A series of workshops will inform the Eawag audience and to ensure that the needs of end-users are addressed. The Sensor Lab will be involved in all discussions regarding software development.

**Software**

Russo, S. (2020). ADASen Labelling Tool (Version 1.0). Eawag: Swiss Federal Institute of Aquatic Science and Technology. https://doi.org/10.25678/0002PC

**Publications**

Stefania Russo, Michael D Besmer, Frank Blumensaat, Damien Bouffard, Andy Disch, Frederik Hammes, Angelika Hess, Moritz Luerig, Blake Matthews, Camille Minaudo, Eberhard Morgenroth, Viet Tran-Khac, Kris Villez. *The value of human data annotation for machine learning based anomaly detection in environmental systems*. Water Research, 206, 2021. https://doi.org/10.1016/j.watres.2021.117695

Stefania Russo, Moritz Luerig, Wenjin Hao, Blake Matthews, Kris Villez. *Active learning for anomaly detection in environmental data*. Environmental Modelling & Software, 134, 2020. https://doi.org/10.1016/j.envsoft.2020.104869

Stefania Russo, Andy Disch, Frank Blumensaat, Kris Villez. *Anomaly detection using deep autoencoders for in-situ wastewater systems monitoring data*. arXiv preprint arXiv:2002.03843, 2020. https://doi.org/10.48550/arXiv.2002.03843

Stefania Russo, Guangyu Li, Kris Villez. *Automated model selection in principal component analysis: A new approach based on the cross-validated ignorance score*. Industrial & Engineering Chemistry Research, 30, 58, 2019. https://doi.org/10.1021/acs.iecr.9b00642


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

### Climis4Aval

Climis4Aval is a joint project of SLF together with SDSC, which aims at cleansing of data coming from the IMIS Network (Intercantonal Measurement and Information System) in order to provide better inputs for operational avalache forecasting.

https://www.datascience.ch/projects/climis4aval

The main goal of the project is to employ machine learning methods in order to:
 * correct biases in the measured data
 * detect outliers and anomalies
 * impute missing data (either on the forecasting basis or using spatial interpolation)

Main outcomes should be:
 * more precise data as inputs to other models used for operational avalanche forecasting
 * statistics published by SLF not skewed by anomalies and outliers
 * providing clean datasets to researchers, thus reducing their overhead in data preparation

The challenging part of the project is the employment of machine learning methods with limited amout of ground truth information. In some cases, the ground truth information is missing completely. We are exploring several different avenues to address this problem. We have annotated some data manually, which gives the possibility to employ supervised machine learning algorithms for time-series data. Where we do not have ground-truth, we are trying to solve the task taking advantage of forecasting algorithms. In these two cases, we are experimenting with some of the state-of-the-art models such as [TCN](https://arxiv.org/abs/1608.08242), [NBeats](https://arxiv.org/abs/1905.10437) and [TimesNet](https://arxiv.org/abs/2210.02186). To impute longer periods without data or as an alternative approach to anomaly detection, we are also looking into spatial interpolation methods. Here, one can go for some classical approaches such as Gaussian Processes, or try to leverage the power of machine learning and experiment with methods such as [CNPs](https://arxiv.org/abs/1807.01613) and its variations, etc.

On the SLF side, the following people are actively involved:
| Name                | Institute | Email                         |
| ------------------- | --------- | ----------------------------- |
| Jan Svoboda         | SLF       | jan.svoboda@slf.ch            |
| Marc Ruesch         | SLF       | ruesch@slf.ch                 |
| David Liechti       | SLF       | david.liechti@slf.ch          |

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
