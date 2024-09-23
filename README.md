# Effectiveness of COVID-19 Vaccines using EMA Clinical Data

### Course: Advanced Statistics for Physics Analysis (2023-2024)
### Master's Degree: Physics of Data, University of Padova (IT)

## Overview

This project was developed as part of the final exam for the Advanced Statistics for Physics Analysis course during the 2023-2024 academic year. The work was carried out in pairs during my second year in the Master's degree program in Physics of Data at the University of Padova.

This project aims to infer the effectiveness of the different COVID-19 vaccines by analyzing clinical trial data provided by the European Medicines Agency (EMA). Using a Bayesian approach, the project models vaccine efficacy in different setups in both vaccinated and placebo groups. The primary goal is to quantify the effectiveness of each vaccine while accounting for uncertainty in the data. The entire analysis is conducted in a single Jupyter Notebook, using rjags to perform Bayesian inference via Markov Chain Monte Carlo (MCMC) sampling.

## Data

Our data source consist in clinical data from the EMA for the following vaccines: 
- [Comirnaty](https://www.ema.europa.eu/en/medicines/human/EPAR/comirnaty)
- [Nuvaxovid](https://www.ema.europa.eu/en/medicines/human/EPAR/nuvaxovid)
- [Spikevax](https://www.ema.europa.eu/en/medicines/human/EPAR/spikevax-previously-covid-19-vaccine-moderna)
- [Ronapreve](https://www.ema.europa.eu/en/medicines/human/EPAR/ronapreve)
- [Xevudy](https://www.ema.europa.eu/en/medicines/human/EPAR/xevudy)

For the first three vaccines the study includes the number of symptomatic COVID-19 cases in both vaccinated and placebo groups. Meanwhile, for Ronapreve and Xevudy vaccines the effectiveness is calculated as a treatment to already infected patients so it includes the number of patients who needed hospitalization in both vaccinated and placebo groups.

## Methodology

Bayesian Model: The model developed assumes the infection/hospitalization rate as a set of bernouilli trials where we have considered a uniform beta prior Beta(1, 1).

Posterior Sampling: The posterior distributions of vaccine effectiveness are estimated using rjags, a tool for Bayesian analysis that leverages Gibbs sampling. This method allows for uncertainty quantification, providing not just point estimates but full posterior distributions of the symptomatic covid/hospilazation rate for both vaccinated and placebo individuals.

Effectiveness Estimate: The vaccine effectiveness is derived by comparing the infection probabilities between vaccinated and placebo groups. The posterior distribution of this effectiveness is used to generate the 95% credibility interval and make probabilistic statements about each vaccine's efficacy.

## Conclusion

This project provides a framework for using Bayesian inference to assess the effectiveness of COVID-19 vaccines based on real-world clinical data. By using a probabilistic approach, the analysis offers a more comprehensive understanding of vaccine performance, moving beyond simple point estimates to account for uncertainty and variability in the data.
