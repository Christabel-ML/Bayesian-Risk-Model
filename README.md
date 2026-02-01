# Fast Made Risk & Decision Making Analysis (Bayesian Networks and Influence Diagrams)

Probabilistic modelling and decision analysis on the fast made manufacturing dataset. 


## Project Overview

This repository contains a complete workflow for analysing manufacturing quality at 'FastMade' and a healthcare treatment scenario through the use of:
- descriptive statistics and feature engineering
- linear regression analysis (predictive and error analysis)
- probability tables and conditional probabilities
- Bayesian networks
- Influence diagrams (expected utility / optimal decisions)

This project forms a submission to the individual coursework component for Risk and Decision making for Data Science and AI


## The Problem
FastMade is a 3D-printing company producing parts where:
- **Flow Rate** and **Temperature** affect **Robustness**
- a **QA Process** probabilistically accepts or rejects parts depending on robustness
- Accepted parts can **break** with robustness-dependent probabilities

The analysis will estimate key probabilities from data and build baysian networks that capture the casual structure and through Influence diagrams, evaluated decisions regarding profit vs compensation risk




## What the presetn Repo Covers

### 1) Data + Regression 
- Load and summarise temperature (Mean and StDev)
- Bin temperature into '{Low, Medium, High}' and compute 'P(TemperatureCategory)'
- Train a linear regression model to predict robustness from temperature category + flow rate, reporting coefficients and MSE


### 2) Probability + Conditional Inference
- Verify P(FlowRate) empirically
- Compute P(Robustness) and P(robustness | Temperature, FlowRate)
- Compute:
    - P(Breaks | Passes QA)
    - P(Weak | Breaks, Passws QA)

### 3) Bayesian Network (PyAgrum)
- Implement a BN with nodes:
    - FlowRate, TemoeratureCategory, Robustness, QA, Breaks
- Compute:
    - Marginal probability of breakage
    - Posterior robustness given evidence (e.g., High flow + Breaks)
    - Relative risk of breakage under low vs high temperature

### 4) Influence Diagram (Decision Analysis)
- Model the 'Keep QA or drop QA' decision
- compute expected profit per product under:
    - QA vs no-QA
    - improved process control (low flow only)
- selective QA using temperature information

### 5) Drug Effectiveness (Simpsons Paradox)
- Build a BN for discoverty time --> Drug choice --> Recovery
- Compute absolute risks and explain why a naive conclusion about effectiveness can be misleading



## Below I list the individual components which make up this Repository

- Fm_CWK1-Copy1.ipynb - main python notebook (contains all analysis and modelling)
- 3d_printing.csv - Dataset usef for the Fast Made analysis
- Assignment1.pdf - assignment brief