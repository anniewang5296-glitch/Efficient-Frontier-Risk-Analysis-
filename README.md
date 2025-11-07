# Portfolio Optimization & Risk Analysis

A comprehensive Python framework for **portfolio optimization using Modern Portfolio Theory (MPT)** and **risk analysis through Value at Risk (VaR) modeling**. This project demonstrates how to construct optimal portfolios, visualize the efficient frontier, optimize risk-return trade-offs, and evaluate portfolio risk using multiple methodologies.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Results](#results)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [License](#license)

## 🎯 Overview

This project provides a complete **portfolio optimization and risk analysis** toolkit that combines:

- **Modern Portfolio Theory (MPT)**: Portfolio optimization using Markowitz mean-variance optimization
- **Efficient Frontier Analysis**: Visualization and construction of optimal risk-return portfolios
- **Portfolio Construction**: Automated finding of maximum Sharpe ratio and minimum volatility portfolios
- **Risk Measurement**: Multiple VaR methodologies for comprehensive risk assessment
- **Model Validation**: Statistical backtesting to evaluate risk model accuracy

### What You Can Do

1. **Optimize Portfolios**: Find optimal asset allocations that maximize risk-adjusted returns or minimize volatility
2. **Visualize Efficient Frontier**: See all possible optimal portfolios and their risk-return trade-offs
3. **Calculate Risk Metrics**: Measure portfolio risk using multiple VaR methods
4. **Validate Models**: Backtest risk models to ensure they accurately predict portfolio risk

The analysis uses Australian equity data (CBA, BHP, TLS) to demonstrate the framework, but the code can be easily adapted for any portfolio of assets.

## ✨ Features

### 1. Portfolio Optimization & Efficient Frontier ⭐

**Core Optimization Capabilities:**
- **Maximum Sharpe Ratio Portfolio**: Automatically finds optimal weights that maximize (Return - Risk-free Rate) / Volatility
- **Minimum Volatility Portfolio**: Identifies the portfolio with the lowest possible risk for given constraints
- **Efficient Frontier Construction**: Generates the complete set of optimal portfolios showing the best possible risk-return combinations
- **Portfolio Weight Optimization**: Uses constrained optimization (SLSQP) to solve for optimal asset allocations
- **Risk-Return Metrics**: Calculates expected returns, volatility, and Sharpe ratios for any portfolio

**Key Features:**
- Long-only constraint (no short selling)
- Fully invested portfolios (weights sum to 1)
- Customizable constraints and bounds
- Visual representation of efficient frontier with optimal portfolios and individual assets

### 2. Risk Measurement & VaR Methodologies

The framework implements four different VaR calculation methods:

1. **Historical VaR** (Non-parametric)
   - Uses historical return distribution quantiles
   - No distributional assumptions
   - Simple and intuitive

2. **Parametric VaR** (Normal distribution)
   - Assumes normal distribution of returns
   - Uses mean and standard deviation
   - Fast computation

3. **Monte Carlo VaR (Uncorrelated)**
   - Simulates portfolio returns using random sampling
   - Assumes independent asset returns
   - Suitable for single-asset or uncorrelated portfolios

4. **Monte Carlo VaR (Correlated)**
   - Incorporates correlation structure using Cholesky decomposition
   - Accounts for multi-asset dependencies
   - Most sophisticated approach for diversified portfolios

### 3. Model Backtesting

Comprehensive validation framework including:

- **Rolling Window Backtesting**: Out-of-sample validation using historical data
- **Violation Rate Analysis**: Compares actual violations to expected rate (5% for 95% VaR)
- **Kupiec Test**: Statistical test for VaR accuracy (p-value > 0.05 indicates good model)
- **Accuracy Metrics**: 
  - Mean Absolute Error (MAE)
  - Root Mean Square Error (RMSE)
  - Average Excess Loss (when VaR is breached)

### 4. Visualizations

**Portfolio Optimization:**
- **Efficient Frontier Plot**: Shows the optimal risk-return curve with all possible portfolios
- **Optimal Portfolio Markers**: Highlights maximum Sharpe and minimum volatility portfolios
- **Individual Asset Plotting**: Displays risk-return characteristics of individual assets

**Risk Analysis:**
- **VaR Backtesting Time Series**: Compares actual losses vs. VaR forecasts over time
- **Cumulative Violations Tracking**: Monitors how violations accumulate vs. expected rate
- **Model Comparison Charts**: Bar charts comparing violation rates, p-values, and RMSE across models
