---
title: "Data Platform for Quantitative Research"
author: Hanlu
date: 2024-11-20
layout: post 
read_time: true
show_date: true
comments: true
share: true
last_modified_at:
excerpt: “A modular data platform built to streamline quantitative research workflows — integrating intraday and fundamental data from APIs like yFinance and Quandl, with custom factor generation, volatility-adjusted signals, and efficient storage in Parquet. Ideal for scalable backtesting and data-driven strategy development.”
---

A modular data platform built to streamline quantitative research workflows — integrating intraday and fundamental data from APIs like yFinance and Quandl, with custom factor generation, volatility-adjusted signals, and efficient storage in Parquet. Ideal for scalable backtesting and data-driven strategy development.


![Architecture Overview](/assets/images/quantplatform-architecture-diagram.png)

## Overview

This project introduces a **modular quantitative research data platform** that streamlines financial data handling from collection to analysis. The system is composed of three major layers:

1. **Data Lake & Catalog**  
   Data from sources like Quandl, Yahoo Finance, and NewsAPI is collected and transformed before being organized in the **Data Lake**. It is labeled with tags and metadata in the **Data Catalog**, enabling efficient lookup and discovery.

2. **Data Workbench**  
   Researchers retrieve time-series or event-based datasets via the **DataWorkbench**, which supports transformation, filtering, and alignment. It also enables reproducible workflows like merging news sentiment with intraday price data.

3. **Data Models & Analysis**  
   Once processed, data is encapsulated into model-ready objects. These can be used in custom pipelines for:
   - Event Study (e.g., news/earnings shocks)
   - Price Prediction
   - Financial Statement Analysis


## Realized Features

- Query and clean stock-level time series (e.g. `close`, `volume`, `EPS`)
- Merge alternative data (e.g. news) with structured financial indicators
- Use customizable event windows and aggregation logic for event studies
- Store processed datasets with versioning and timestamping
- Compatible with third-party APIs and manual uploads


## Event Study: Example Usage

The platform enables event-driven analysis such as price reactions to news or earnings releases. The following example shows how to run an intraday **Event Study** on Apple Inc. (AAPL):


```python
# Initialize modules
event_study = EventStudy(...)

# Run analysis
news, intraday = event_study.retrieve_data(ticker="AAPL", ...)
aggregated = event_study.aggregate_intraday_data(interval="30min")
impact_df = event_study.analyze_event_impact(news, aggregated, event_window=60)

# Visualize results
event_study.visualize_event_impact(impact_df)
```

![png](/assets/images/event_impact_plot.png){: .center-image }
This plot illustrates average price movements around event timestamps (e.g. news headlines). A noticeable shift in the mean price shortly after the event indicates a price reaction window and validates the impact.

## Use Cases

- **Backtest financial signals** on pre-cleaned datasets  
- **Perform event studies** on earnings, M&A, or macro news  
- **Forecast intraday volatility** or return series using machine learning models  
- **Generate alpha** from alternative datasets with structured APIs

➡️ Explore the full project and source code on [GitHub](https://github.com/HanluGe/Data-Platform-for-Quantitative-Research)