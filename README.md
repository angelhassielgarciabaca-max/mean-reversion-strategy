# Quantitative Stationarity & Mean-Reversion Framework

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

##  Overview
This repository contains a quantitative finance framework designed to analyze and exploit non-stationary financial time series by identifying temporary windows of **local stationarity**. 

Rather than treating the market as a globally constant system, this approach views it through the lens of **Complex Systems Economics**—where millions of decentralized, independent agents interact in parallel, influenced by exogenous shocks and speculative feedback loops.

---

##  Core Methodology

1. **Log Returns & Stationarity Transformation**: 
   - Processing raw asset prices into logarithmic returns to stabilize variance.
   - Identifying temporal boundaries where statistical properties (mean and variance) remain locally constant.

2. **Ornstein-Uhlenbeck (OU) Stochastic Processes**:
   - Utilizing the continuous-time stochastic differential equation (SDE) to model mean-reverting behavior and capture the "restoring force" pulling asset spreads back toward their equilibrium center of gravity ($\mu$):
     $$dX_t = \theta (\mu - X_t) dt + \sigma dW_t$$

3. **Deep Learning for Regime Classification**:
   - Deploying neural network architectures to detect localized regimes of stationarity, simplifying execution signals for long/short entry and exit rules.

4. **Half-Life Decay Analysis**:
   - Calculating the anomaly's half-life decay ($t_{1/2} = \frac{\ln(2)}{\theta}$) to dynamically measure how long an inefficiency persists before degrading, optimizing holding periods and mitigating alpha decay.

---

##  Repository Structure

```text
├── notebooks/
│   └── ou_stationarity_analysis.ipynb   # Main interactive pipeline (Ornstein-Uhlenbeck & Deep Learning)
├── src/
│   ├── data_processor.py                # Log returns calculation and stationarity tests
│   ├── ou_estimator.py                  # Maximum Likelihood Estimation for OU parameters & Half-Life
│   └── models.py                        # Neural network architectures for local regime detection
├── requirements.txt                     # Project dependencies
└── README.md
