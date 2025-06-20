---
title: "Data Platform for Quantitative Research"
hidden: true
last_modified_at:
excerpt: “A modular data platform built to streamline quantitative research workflows — integrating intraday and fundamental data from APIs like yFinance and Quandl, with custom factor generation, volatility-adjusted signals, and efficient storage in Parquet. Ideal for scalable backtesting and data-driven strategy development.”
---


## Overview

This project builds a modular **quantitative research data platform**, integrating:

- 🧱 **DataLake** for centralized storage of financial datasets  
- 📚 **DataCatalog** for intuitive dataset discovery by category and metadata  
- 🧪 **DataWorkbench** for retrieval, transformation, and backtesting  
- 📰 **EventStudy** module linking news sentiment and intraday price impact  
- 📈 Support for **price-volume**, **fundamentals**, and **alternative datasets**

---

## Features

- 🔍 Query and clean stock-level time series (e.g. `close`, `volume`, `EPS`) via `DataWorkbench`
- 📰 Sentiment analysis using news headlines and event windows
- 🕒 Intraday event impact visualization with customizable aggregation (e.g. 30min)
- 💾 Custom storage for processed datasets with versioning
- 📁 Compatible with `Quandl`, `Yahoo Finance`, and user-curated data

---

## Example Use Cases

- Backtest trading strategies based on **financial signals**  
- Perform **event studies** on earnings/news  
- Integrate high/low frequency data for **volatility-aware position sizing**

---

## Try It

See the full README in the GitHub repository for code examples and setup:  
👉 [View on GitHub](https://github.com/HanluGe/Data-Platform-for-Quantitative-Research)
