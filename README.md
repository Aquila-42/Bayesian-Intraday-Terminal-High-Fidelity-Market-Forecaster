# 📈 High-Fidelity Bayesian Trading Terminal

A real-time intraday analysis tool that combines **Bayesian Inference** with professional-grade financial visualization. This terminal is designed to stream 1-minute interval data and provide a 60-second forward-looking price target based on local volatility and momentum.

## 🚀 The Concept
I built this because most retail indicators are lagging. I wanted to create a "Live Terminal" that uses **Bayesian Ridge Regression** to provide not just a price target, but a statistical confidence interval ($\pm \sigma$) for the next minute of trading.



---

## 🛠️ Technical Architecture

### 1. The Bayesian Prediction Engine
Unlike standard OLS regression, the **Bayesian Ridge** model treats coefficients as probability distributions. 
* **Feature Set:** Uses Log Returns, 5-minute Momentum, and 20-minute Rolling Volatility.
* **Preprocessing:** Implements `RobustScaler` to handle the "fat-tail" outliers common in intraday flash-moves.
* **The Result:** Provides a target price ($P_{t+1}$) and a variance parameter ($\sigma$) to measure signal uncertainty.

### 2. Professional Visualization (`mplfinance`)
The UI is styled after institutional trading platforms (Dark-Mode / Binance style):
* **Candlestick Rendering:** High-fidelity OHLC candles.
* **Technical Overlay:** 9-period Exponential Moving Average (EMA).
* **Live Annotation:** Real-time price and AI-target labels mapped directly onto the y-axis for zero-latency interpretation.



---

## 🧰 Tech Stack
* **Language:** Python 3.x
* **Finance:** `yfinance`, `mplfinance`
* **ML/Math:** `scikit-learn` (BayesianRidge), `NumPy`, `Pandas`
* **Plotting:** `Matplotlib` (Custom binance-style dark theme)

## 🧪 The "Fun" Part
The best part of this build was the **Intraday Data Slicing**. By limiting the view to the last 35 minutes of 1-minute candles, the terminal creates a high-zoom "microstructure" view that makes market noise look like a structured physical process.

---
*Built to explore the intersection of Bayesian Statistics and High-Frequency Data.*
