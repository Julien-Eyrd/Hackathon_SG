# 📈 Market Sentiment & Stock Correlation: Société Générale Hackathon

[![Python](https://img.shields.io/badge/Language-Python-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![NLP](https://img.shields.io/badge/Model-FinBERT%20%2F%20TextBlob-lightgrey?style=flat)](https://huggingface.co/ProsusAI/finbert)
[![Scraping](https://img.shields.io/badge/Pipeline-Web__Scraping-orange)](https://en.wikipedia.org/wiki/Web_scraping)

An end-to-end financial data science pipeline developed for the **Société Générale Hackathon**. This project scrapes alternative data text streams (Reddit discussions and Bloomberg financial articles) to extract market sentiment using state-of-the-art NLP models, correlating the data with stock metrics to forecast volatility and directional trends.

---

## 📌 Table of Contents
* [Project Overview](#-project-overview)
* [Data Engineering & Scraping](#-data-engineering--scraping)
* [Sentiment Analysis Pipeline](#-sentiment-analysis-pipeline)
* [Methodology & Correlation](#-methodology--correlation)
* [Interactive Dashboard](#-interactive-dashboard)

---

## 🔍 Project Overview

Traditional market indicators often lag behind fast-moving, crowd-sourced retail momentum and flash financial journalism. 

**Objective:** Build an automated pipeline to scrape retail investor boards and institutional news, extract dense text sentiment profiles, and analyze their correlation with financial asset behavior to deliver alpha-generating trading signals.

---

## 📊 Data Engineering & Scraping

The repository handles real-time data collection through specialized scripts:
* **Reddit Scraping:** Implements cross-platform search engines (`reddit_scraper.py` and an optimized `reddit_scraper_quick.py`) to gather discussion threads, metadata, and timestamps from active trading communities.
* **Bloomberg & Finance News:** Scrapes professional institutional media channels (`scrape_finance_articles.py` and `scrape_data.py`) to keep track of financial journalism article counts and body text.
* **Target Filtering:** Isolates specific asset dimensions dynamically using localized financial watchlists (`stock_keywords.py`).

---

## 🧠 Sentiment Analysis Pipeline

To extract precise trading sentiments from highly chaotic text datasets, we built and compared a multi-tiered Natural Language Processing (NLP) framework:
1. **FinBERT (`sentiment_analysis_finbert.py`):** A specialized BERT architecture pre-trained on massive financial corpora, utilized to robustly classify fine-grained financial tones (positive, negative, neutral).
2. **TextBlob (`sentiment_analysis_textblob.py`):** A lightweight, lexicon-based approach utilized to evaluate structural text polarity and subjectivity scores at scale.
3. **Hybrid Mixing Layer (`sentiment_analysis_mix.py`):** Combines neural and algorithmic sentiment streams to stabilize prediction bounds.

---

## ⚙️ Methodology & Correlation

Once textual signals are engineered into continuous rolling variables, they are merged with structural market feeds (`stock_data/`):
* **The High-Dimensionality Space:** Text processing paired with cross-platform indicators expands our feature space drastically. We handle this bottleneck using regularized regression modeling configurations (Lasso/Ridge frameworks) to drop uninformative text windows.
* **Imbalance & Threshold Tuning:** Sudden market volatility shifts or sharp equity up/down movements are naturally imbalanced events. Shifting decision boundaries away from standard $0.5$ cutoffs optimizes the model's **F1-score**, balancing trade sensitivity (**Recall**) with algorithmic precision.
* **Statistical Alignment (`correlation.py`):** Computes directional correlations between rolling sentiment intensity variations and underlying options/stock volatility signatures.

---

## 💻 Interactive Dashboard

The repository includes a web-based, real-time analytics interface (`dashboard.py`). The dashboard allows portfolio managers and quantitative traders to visualize rolling sentiment indexes, track article volume spikes, and monitor active correlation signals directly within an interactive workspace.

