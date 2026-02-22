# Algorithmic Trading Strategy Optimization: RSI & SMA

## Executive Summary
This repository contains a quantitative algorithmic trading backtester designed to evaluate and optimize momentum and trend-following strategies on high-frequency cryptocurrency data. Specifically, it models a hybrid strategy utilizing the Relative Strength Index (RSI) for entry signals and Simple Moving Average (SMA) for exit signals, applied to 15-minute timeframe Bitcoin (BTC) market data.

## Strategy Methodology & Logic

### 1. Signal Generation
* **Entry Signal (Buy):** The strategy identifies oversold conditions utilizing the Relative Strength Index (RSI). A buy signal is triggered when the RSI crosses below an optimized threshold.
  
  $$RSI = 100 - \frac{100}{1 + RS}$$
  *(where RS is the average gain of up periods during the specified timeframe divided by the average loss of down periods)*

* **Exit Signal (Sell):** The strategy employs a Simple Moving Average (SMA) crossover to secure profits and manage downside risk. A sell signal is executed when the closing price crosses the SMA line.
  
  $$SMA_n = \frac{1}{n} \sum_{i=1}^{n} P_i$$
  *(where $P_i$ is the closing price and $n$ is the moving average window)*

### 2. Parameter Optimization & Backtesting
* **Grid Search:** The model programmatically iterates through multiple combinations of RSI lengths, RSI thresholds, and SMA windows to identify the parameter set that yields the highest risk-adjusted return.
* **Benchmarking:** The cumulative returns of the optimized algorithmic strategy are plotted and rigorously benchmarked against a traditional **Buy and Hold** strategy to evaluate true alpha generation.

## Technical Infrastructure
* **Core Language:** Python
* **Data Retrieval & Manipulation:** `requests`, `pandas`, `numpy`
* **Performance Visualization:** `matplotlib` (Cumulative Returns Comparison)
* **Domain:** Algorithmic Trading, Backtesting, High-Frequency Data (15m intervals), Crypto Market Microstructure
