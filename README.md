# Contrails Analysis Workshop

> All times in BST / UTC+1

- **Date**: 2024 June 19 - 21
- **Location**:
  [Google, 3rd Floor, 123 Buckingham Palace Road, London SW1W 9SH](https://maps.app.goo.gl/MvXRfKy9FNf6PvuJ8)
- [Agenda](Agenda.pdf) (pdf)
- [Presentations](#presentations)
- [Labs](#labs)

## Presentations

### Wednesday, June 19, 2024

#### Observation of contrail formation (09:30 - 10:30)

- **Phillippe Very** (Eurocontrol): _The ContrailNet Portal: Stimulating
  Contrail Research by Sharing Data_

  The ContrailNet initiative aims to integrate the work of different
  contrail-related projects and share valuable, sometimes costly, data to avoid
  duplication of effort and to stimulate collaboration and research in the field
  of contrail science. The scope has been extended to a global collaboration.
  The focus is on sharing high quality labelled data sets, especially those that
  require manual validation. After introducing the initiative, this presentation
  will focus on datasets of long sequences (1-2 hours) of human-labelled ground
  camera images that will be useful to better understand the evolution of
  persistent contrails.

- **Olivier Liandrat** (Reuniwatt): _Observation of clouds and contrails using
  sky imagers_

  Reuniwatt's expertise is to monitor the presence and characteristics of clouds
  and to forecast their location in the next minutes, hours and/or days. We rely
  on three core technologies: our patented visible and thermal ground-based sky
  imagers, meteorogolical satellite observations and numerical weather
  prediction models. In this presentation, we will share our experience
  regarding the observation of clouds and contrails from the ground.

  https://www.reuniwatt.com

  https://reuniwatt.com/en/wp-content/uploads/sites/3/2023/08/MTI_SEPT2023_SkyImager_for_Contrail_Observation.pdf

- **Aaron Sarna** (Google): _Contrail Attribution in Geostationary Satellite
  Imagery_

  I'll discuss the challenges of attributing contrails detected in geostationary
  satellite imagery to the flights that made them, and present a new algorithm
  for doing so. I'll also present a new approach for evaluating attribution
  algorithms, given the lack of abundant ground truth labels.

#### Observation of contrail formation (10:45 - 12:00)

- **Remi Chevallier** (Airbus/ENAC): _A Simple and Cost-Effective Method for
  Contrails Ground Observation: Application in Concept of Operations Feasibility
  Studies_

  Condensation trails have a significant climate impact, and we are seeing a
  large number of initiatives to help mitigate this impact, proposing a large
  variety of concepts of operations (CONOPS). These are still today subject to a
  certain number of uncertainties (weather forecasts, contrail impact prediction
  models, potential flight delays, trajectory changes driven by air traffic
  control etc…). Each CONOPS may result in increased fuel consumption, greater
  airspace congestion, and additional constraints for airlines, such as the need
  for the ability to implement trajectory re-planning shortly before takeoff or
  even during flight.

  There is a tradeoff between the additional costs and constraints and the
  potential climate benefits offered by the contrail impact mitigation methods.
  Each source of uncertainty could indeed reduce the potential climate benefits
  of the CONOPS. It is crucial to identify and quantify all potential costs and
  constraints through simulations and observations. This validation process will
  help airlines and ANSP implement concepts of operations effectively. Airbus is
  working on both simulations and observations studies. This presentation will
  showcase one of our observation-related studies and demonstrate its
  application in the context of CONOPS validation.

  Geostationary satellite observations are currently used by several actors.
  However, they lack the capability to observe contrails formation because of
  their lack of spatial resolution. Ground-based observation could address this
  issue, but it requires a substantial number of observation sources to conduct
  an effective campaign. To meet this need, we developed a simple and
  cost-effective method for contrail observation using a basic smartphone
  camera. Our approach includes a lightweight contrail detection model optimized
  for inference on affordable devices. Combining these ground-based observations
  with air traffic data enables the identification of aircraft producing
  contrails, the study of contrail formation conditions, and comparisons with
  contrail prediction models. This could prove valuable in the CONOPS validation
  process.

- **Wouter Vandenneuker** (MUAC): _Prototyping a Contrail Camera Network: From
  Concept to Reality_

  Satellites track long-lasting contrails but lack real-time feedback and
  aircraft identification. At Eurocontrol MUAC, we built a contrail ground
  camera to support contrail mitigation trials. We present valuable insights
  from over a year of observations with webcams and machine learning in our
  airspace.

- **Luc Busquin** (Alaska Airlines): _Using Global Meteor Network Cameras for
  Contrail Observation_

  In this presentation, I will introduce a project focused on leveraging the
  Global Meteor Network (GMN) for contrail observation. The GMN, with its
  existing network of approximately 1000 cameras worldwide, offers a unique
  opportunity to enhance contrail research.

  This project explores the potential of adding contrail observation
  capabilities to the GMN camera stations. By utilizing the existing GMN
  infrastructure, we aim to develop a cost-effective and efficient method for
  continuous day and night contrail observation without interrupting meteor
  research.

  I will cover the technical aspects of adapting GMN cameras for contrail
  monitoring. Preliminary results from our project will be shared, demonstrating
  the effectiveness of this approach in capturing contrail data alongside meteor
  observations.

  By integrating GMN resources into contrail research, we can significantly
  improve our observational capabilities, especially regarding the issue of
  contrail attribution.

  https://youtu.be/DUIoQJUn1YU?si=lDnodF6PhqrCzC-o

  https://youtu.be/6JxqNqtUJQc?si=lgmpSxUWxiT7MpBP

- **Peter DeBock** (ARPA-E), **Miad Yazdani** (RTX), **Saikat Majumder** (GE):
  _ARPA-E PRE-TRAILS (Predicting Real-time Emissions Technologies Reducing
  Aircraft Induced Lines in the Sky)_

  ARPA-E launched a program to develop novel high accuracy sensing mechanisms,
  data fusion and observation mechanisms to predict aircraft induced cirrus with
  high accuracy. Five teams were funded with diverse approaches to develop and
  demonstrate these technologies.

  https://arpa-e.energy.gov/technologies/exploratory-topics/aviation-contrails

#### Evaluating forecasts (13:00 - 14:20)

- **Vincent Meijer** (TUDelft): _Contrail forecast evaluation using satellite
  data_

  We construct a dataset of flight waypoints matched to contrails and not
  matched to contrails using CALIOP LIDAR observations of contrails collocated
  with GOES-16 ABI data. We also develop a contrail forecast evaluation
  framework that can directly capture the potential benefits of contrail
  avoidance and use the constructed dataset to evaluate these benefits for two
  numerical weather prediction products and a satellite-based nowcasting system.

- **Scott Geraedts** (Google): _ContrailBench: datasets for forecast evaluation_

  Showcasing how we can use observations to compare contrail forecasts to each
  other, and proposing a public model comparison framework.

- **Greg Thompson, Adam Durant** (Satavia): _On the fidelity of high-resolution
  numerical weather forecasts of contrail-favorable conditions_

  The potential climate-warming impact from aircraft contrails may be similar in
  magnitude to the direct effect from carbon dioxide emissions across all
  aviation. The warming impact may be mitigated through pre-tactical flight
  trajectory optimization to avoid ice supersaturation regions (ISSRs) while
  also considering aircraft performance and CO2 emissions. The ability to
  perform such deviations depends on accurate predictions of water vapor in the
  upper troposphere and lower stratosphere (UTLS). Herein we evaluated the
  performance of two leading global numerical weather prediction (NWP) models:
  the Global Forecast System (GFS) developed in the USA and the Integrated
  Forecast System, (IFS) developed in Europe, and a research mesoscale model,
  Weather Research and Forecasting configured by SATAVIA (S‐WRF) to predict UTLS
  moisture and ISSR. We compared humidity forecasts to observations from 383
  aircraft flights and 3480 radiosonde profiles comprising approximately 1.5
  million measurements over Europe and the Middle East for 10 months in 2022.
  Neither GFS nor IFS properly reproduced the observed distribution of relative
  humidity with respect to ice (RHice). Moreover, in addition to not being
  usable for prospective flight planning, the ERA5 reanalysis only slightly
  improved the outcome of the IFS. Only the S‐WRF model with multi-moment cloud
  physics and high spatial resolution (5 km grid spacing) closely reproduced the
  observed relative frequency distribution of RHice. Furthermore, ISSR
  validation using near equal-area neighborhoods when computing Matthews
  Correlation Coefficient and F1 score showed that S‐WRF scored higher (F1 =
  0.66) than the IFS (F1 = 0.62), while the GFS had near zero score due to its
  near complete lack of predictions of RHice greater than 100% in stark contrast
  to observations. In fact, S‐WRF also correctly predicts 92% of the time when
  conditions were not conducive to contrail formation. Ultimately, the S‐WRF
  model could be used to alter flight plans to deviate above or below nearly
  certain contrail formation regions to reduce non-CO2 climate impacts of
  aviation.

- **Sebastian Eastham** (Imperial): _Using LIDAR to analyze and evaluate
  contrail models_

  One of the major sources of uncertainty in the climate impact resulting from
  contrails is how the contrail develop over time, in large part because it is
  so challenging to measure the physical and optical properties of contrails.
  Similarly, the high uncertainty in meteorological data makes it difficult to
  evaluate whether or not discrepancies between observed and modelled contrails
  are due to the input conditions or due to inaccuracy in the contrail model. We
  use observational data from satellite LIDAR to test two contrail models, first
  using ERA5 data but then using the models to infer the most likely
  meteorological conditions. Our results show large differences in the radiative
  forcing estimated by different models for the same conditions, but that this
  is in part driven by differences in the sensitivity of those models to the
  local conditions. This divergence in sensitivity to parameters such as local
  relative humidity suggests that current approaches to identify high- or
  low-impact flights may be unreliable and that more work is needed to establish
  robust, high-speed contrail models which can support such analyses.

#### Operational Evaluation (14:40 - 16:00)

- **Christiane Voigt** (DLR): _New results on contrails, SAF and lean burn
  engine technology from recent aircraft campaigns_
- **Aarón Sonabend** (Google), **Tom Dean** (BE): _Evaluating preliminary
  avoidance trials_
- **Louis Robion, Prashanth Prakash** (MIT): _Leveraging contrail observations
  and measurements from flight campaigns_

  The presentation will focus on approaches to leverage the growing contrail
  observation data and associated techniques and measurements from flight
  campaigns to improve models and bound modeling uncertainties. The presentation
  will also briefly cover the use of the MIT Contrail Avoidance Support Tool
  (MCAST) as a research tool to further our understanding of problems in
  contrail observations.

- **Dennis Piontek, Kai Widmaier** (DLR): _First results for the AKKL
  100-flights-trial & CONCERTO_

  We present recent work on two ongoing projects: the German AKKL
  100-flights-trial and the SESAR project CONCERTO. AKKL focusses on developing
  and testing procedures and strategies to operationally avoid
  contrail-sensitive airspaces by airspace users. Four airlines and two flight
  trajectory optimizers are taking part in this project, and the first contrail
  avoidance flights were conducted in spring 2024. We present first post-flight
  analysis data. The SESAR project CONCERTO focusses on developing indicators
  and tools to select flight with potentially high climate impact and high
  mitigation potential. The development focusses on air navigation service
  providers and in particular flow managers. Here we present recent studies on
  CoCiP uncertainties carried out in this context.

#### Reflecting on Day 1's learnings (16:00 - 17:00)

- **Shelagh McLellan** (Google): _Breakout groups - small group discussion with
  guided questions_

---

### Thursday, June 20, 2024

#### New forecast and planning approaches (09:00 - 10:20)

- **Axel Seifert** (DWD): _A two-moment cloud ice scheme in the ICON model for
  predicting ice supersaturation_

  I will present the new two-moment cloud ice scheme of the ICON model that has
  been developed to explicitly predict ice supersaturation in the upper
  troposphere. By predicting ice crystal number concentration the model has a
  better representation of the phase relaxation time and, hence, ice
  supersaturation. This provides an alternative approach to the parameterization
  in ECMWF's IFS model, which allows only supersaturation in the cloud-free
  area. Verification with radiosondes shows that both models have a similar
  skill in predicting ice supersaturation. The makes this new ICON version a
  viable alternative for providing meteorological input for contrail prediction
  models.

- **Zane Dedekind** (Environment Canada): _Reducing the Impact of Aircraft
  Induced Clouds on Climate – Development of the Contrail Avoidance Tool (CoAT)_

  Aviation's rapid global growth presents significant sustainability challenges
  in alignment with the Paris Climate Agreement (Grewe et al., 2021). In
  addition to CO2 emissions, non-CO2 effects, notably from contrail cirrus and
  nitrogen oxides, contribute to the globally averaged climate forcing share of
  ~ 3.5% (Lee et al., 2021), with the majority arising from non-CO2 effects
  (Kärcher, 2018). Contrail cirrus exerts a net warming radiative effect
  (Forster et al., 2012; Teoh et al., 2022a), contributing an effective
  radiative forcing (ERF) of 57 mW m−2 in 2018, the largest among
  aviation-induced emissions (Lee et al., 2021). However, the impact of contrail
  cirrus within these non-CO2 effects carries a large uncertainty. To address
  the uncertainty, we are developing a Contrail Avoidance Tool (CoAT) based on
  Environment and Climate Change Canada (ECCC) operational numerical weather
  prediction (NWP) modeling systems using the Global Environmental Multiscale
  (GEM) atmospheric model (Côté et al., 1998; Girard et al., 2014). The core of
  CoAT is based defining contrail formation regions using the Schmidt-Appleman
  Criteria (Schumann, 1996) and then calculating the properties of young
  contrails (Unterstrasser, 2016) which is then advected by the NWP model. The
  CoAT is being tested on the High-Resolution Deterministic Prediction System
  (HRDPS; Milbrandt et al., 2016) at a horizontal resolution of 1 km x 1 km,
  before being employed over the pan-Canadian domain, which is run four times
  daily with 48-hour forecasts. CoAT will then be adapted for the Global
  Deterministic Prediction System (GDPS; Buehner et al., 2015), which is run
  twice daily with 10-day forecasts, thereby providing coverage for Canadian
  airspace and the Atlantic and Arctic Ocean regions with the densest flight
  routes.

- **Zeb Engberg** (BE), **Tharun Sankar** (Google): _A hybrid contrail forecast
  model_

  We present the development and application of a generalized 4D contrail impact
  forecast. The contrail forecast is the hybrid of two individual models: (1)
  Google Research forecast of regions with high probability of contrail
  formation; and (2) Breakthrough Energy forecast of regions with highly warming
  contrails.

  Google Research has developed a data-driven forecast system for contrail
  formation, utilizing contrail detections in satellite imagery. This approach
  leverages machine learning algorithms and integrates weather data as inputs to
  predict the probability that an aircraft generates a contrail visible in the
  GOES satellite imagery as it passes through a specific region of the
  atmosphere. Breakthrough Energy has developed a physics-based forecast of
  contrail climate forcing on a regular grid based on the Contrail Cirrus
  Prediction (CoCiP) model. The gridded CoCiP model operates deterministically,
  relying on three inputs: meteorology, aircraft performance, and epistemic
  model parameters describing the governing atmospheric physics.

  The combined hybrid forecast model generates real-time expected values of
  contrail climate forcing provided on a regular grid in standard meteorological
  formats (NetCDF, GRIB). We present an overview of each individual model and
  the approach to synthesizing the models to produce a single probablistic
  forecast of contrail formation and climate forcing.

- **Alejandra Frias-Martin** (Flightkeys): _Implementation of contrail avoidance
  in commercial flight planning_

  How is contrail avoidance being implemented in flight planning? What has
  changed in the last year and what is predicted to change in the year to come?
  What do airlines think? All these questions will be answered in this
  presentation.

#### Observations of Climate Forcing (11:00 - 12:00)

- **Ollie Driver** (Imperial): _Factors influencing contrail observability in
  satellite images_

  Not every contrail is observable in satellite imagery, due to either sub-pixel
  structure or low optical depth. In this study, the contrail observability
  threshold is assessed as a function of the contrail’s properties and the
  imager used. Synthetic satellite images were created using radiative transfer
  simulations of simple linear contrails in clear sky. Their detectability was
  tested using a detection algorithm tuned to a labelled dataset to derive a
  threshold for detectable contrails in terms of their properties.

  The analysis was combined with a modelled global contrail population to
  determine the fraction of contrails, and of contrail radiative forcing, that
  is observable. It was shown that the most strongly warming contrails are also
  more easily detectable than other contrails, but that significant fractions of
  climate-relevant contrails are not detected using current techniques and
  instruments. The detectability of contrails as their properties evolve is also
  explored, finding that most contrails are observable at some point in their
  lifecycle, with the onset of detection typically within the first two hours.
  This work applies to future design of experimental trials—optimising for
  strongly-observable outcomes—as well as being readily expandable to future
  detection algorithms, backgrounds, and observations.

- **Xinyue Wang** (Climaviation): _Estimating the radiative effect of contrail
  outbreaks by using geostationary satellite observations_

  Estimation of the perturbation to the Earth's energy budget by contrail
  outbreaks is required for estimating the climate impact of aviation and
  verifying the climate benefits of proposed contrail avoidance strategies such
  as aircraft rerouting. Here we identified two successive large-scale contrail
  outbreaks developing in clear-sky conditions in geostationary and
  polar-orbiting satellite infrared images of Western Europe lasting from 22–23
  June 2020. Their hourly cloud radiative effect, obtained using geostationary
  satellite cloud retrievals and radiative transfer calculations, is negative or
  weakly positive during daytime and positive during nighttime. The cumulative
  energy forcing of the two outbreaks is 7 PJ and −8.5 PJ, with uncertainties of
  3 PJ, stemming each from approximately 15–20 flights over periods of 19 and 7
  hr, respectively. This study suggests that an automated quantification of
  contrail outbreak radiative effect is possible, at least for contrails forming
  in clear sky conditions. We are currently working on enhancing the method for
  more complicated cloud systems, such as 2-layer cases with a uniform liquid
  cloud layer below and contrails above, coexisting with surrounding
  single-layer liquid clouds and ice clouds. These cases are being tested with
  new data obtained from EUMETSAT.

  https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2024GL108452

- **Kevin McCloskey, Aarón Sonabend** (Google): _12hr satellite-driven contrail
  flux via causal inference_

## Labs

### Thursday, June 20, 2024

#### Session 1 (13:00 - 14:00)

- **Scott Geraedts** (Google): _Using ContrailBench_

  In this lab the participant will load public, observational datasets, and use
  them to evaluate different contrail forecasts.

#### Session 2 (14:00 - 15:00)

- **Nick Masson, Tom Dean** (BE): _Contrails Observer app hackathon_

  We'll go spelunking in a handful of compelling datasets, with our initial
  bearing centered on images captured by the
  [Contrails Observer App](https://play.google.com/store/apps/details?id=com.breakthrough.contrails&hl=en_US)
  (iOS and Android), a mobile phone app for community-generated observations of
  contrails.

  Curated datasets include:

  - Contrail App images (where people see contrails!)
  - ADS-B waypoints (where the airplanes are at!)
  - `pycontrails` CoCiP polygons (where we expect contrails should be)
  - GOES contrail-detections (where satellites + computer vision see contrails)
  - GOES full-disk and mesocale images (where satellites are collecting imagery)

  https://github.com/contrailcirrus/2024-06-contrails-workshop/blob/main/labs/observer_app_hackathon/INTRO.md

- **Seb Eastham** (Imperial), **Tristan Abbott** (BE): _Getting set up with
  APCEMM_

  This lab will provide an introduction to simulating contrails using the
  Aircraft Plume Chemistry Emission and Microphysics Model (APCEMM,
  https://github.com/MIT-LAE/APCEMM), an intermediate-complexity model that aims
  to bridge the gap between Gaussian plume models and computationally-expensive
  large eddy simulations. We will begin by using a case study with idealized
  meteorology to demonstrate how input data for an APCEMM simulation is
  formatted, how an APCEMM simulation is run, and how APCEMM output files are
  organized. We will them demonstrate how a new pycontrails interface to the
  APCEMM model can be used to run APCEMM simulations for a real flight using
  real meteorological fields. Any remaining time can be used to discuss
  potential use cases and pycontrails or APCEMM features needed to support them.
  Attendees will leave this lab with the ability to configure and run APCEMM
  simulations and parse APCEMM output for comparison with other contrail models
  or observations.

#### Session 3 (15:00 - 16:00)

- **Nick Masson** (BE), **Shelagh McLellan** (Google): _User stories: Designing
  effective data, interfaces, and products_

  "If you build it, they will come". While this might fly for Kevin Costner, it
  does poorly to describe adoption of technology in the "real world." In this
  interactive discussion based lab, participants will write user stories — a
  common tool in product development for designing more user-centered
  technology. We’ll also explore barriers to adopting contrail
  forecasts/nowcasts, and monitoring, reporting and verification (MRV) tools for
  managing and complying with targets for non-CO2 climate impacts. By the end of
  this lab you’ll gain greater empathy for users, and have a toolkit that you
  can apply in your own work to better drive user engagement.

- **Zeb Engberg, Tristan Abbott** (BE): _Finding flights in Landsat and
  Sentinel_

  Validating contrail prediction models requires observations of contrail
  evolution from formation to dissipation. This lab introduces new pycontrails
  tools for observing the earliest stages of the contrail lifecycle by
  intersecting flights with high-resolution (10-30 m) Landsat and Sentinel-2
  satellite imagery. We will begin with an overview of the Landsat and
  Sentinel-2 platforms, then show how to use BigQuery to efficiently find
  satellite scenes that contain commercial aircraft. We will then use a small
  number of scenes as case studies to demonstrate that aircraft and
  newly-emitted contrails can readily be geolocated and identified in Landsat
  and Sentinel-2 imagery. Attendees will leave this lab able to efficiently
  search and download Landsat and Sentinel-2 data and visualize young contrails
  in single-band and composite imagery.
