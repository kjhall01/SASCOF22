# SASCOF 2022: Seasonal Forecasts of Summer Monsoon Rainfall with Extreme Learning Machine 
### By Nachiketa Acharya & Kyle Hall

Here we present both deterministic and probabilistic seasonal forecasts of Summer Monsoon Rainfall (SMR) over the South Asia region. This rainfall occurs during the JJAS season, and is characterized by high interannual variability, which presents a significant forecasting challenge. 

These forecasts are produced using Extreme Learning Machine (ELM) based Multi-Model Ensembles. ELM is a neural network-based non-linear regression method, which serves as a fast alternative to the traditional Single Layer Feed-Forward neural network. (Huang et al, 20??) Since ELM is designed to produce deterministic forecasts, we have used a modified version known as Probabilistic Output ELM (POELM) to produce probabilistic forecasts. POELM replaces the linear objective function of ELM with a sigmoid objective function, and uses sigmoid additive hidden neurons. (POELM paper, 2018) Here, we have also altered the hidden neurons of POELM to use different types of activation functions, and adopted a postprocessing rule using normalization and softmax to ensure that the tercile probabilities are reasonable. (Pending publication) 

# Summer Monsoon Rainfall 2022 Forecast: 

<div align='center'>
 <img src="https://github.com/kjhall01/SASCOF22/blob/master/2022forecast.png?raw=true" alt="fcst"/>
</div>


### Experimental Design: 

**Predictors:** 4 North American Multi-Model Ensemble (NMME) models - CCSM4, CFSv2, NASA-GEOS, and CANSIPS-IC3    

**Predictand:** SASCOF observed JJAS precipitation

**Training Period:** 1982-2019 

**Hyper-Parameters:** 
 - 5 hidden layer neurons using ReLu activation
 - MinMax scaling to (-1, 1) of predictors 
 - Simple anomaly scaling of predictand
 - One-Hot Encoding of predictand for POELM 
 - Cross Validation Window: 3 years (Leave-3yrs-Out Crossvalidation)
 - 3x3 Gaussian Kernel Smoothing of output

<div align='center'>
 <img src="https://github.com/kjhall01/SASCOF22/blob/master/skillmetrics.png?raw=true" alt="skill"/>
</div>
<p align='center'>
  <b>Leave-3-Out Cross-Validated Skill Metrics</b>
</p>


