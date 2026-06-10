<p align="center">
  <img src="assets/banner.png" alt="Energy Forecast AI Banner" width="100%">
</p>

# ⚡ Attention-Based BiLSTM for Multi-Target Renewable Energy and Load Forecasting

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow 2.x](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://tensorflow.org)
[![Deep Learning](https://img.shields.io/badge/Category-Deep%20Learning-green.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Conference: CONFLUENCE 2026](https://img.shields.io/badge/Conference-CONFLUENCE%202026-red.svg)](#)

A high-performance deep learning framework for multi-target energy forecasting, featuring a custom **Attention-based Bidirectional LSTM (BiLSTM)** architecture. Originally presented at the **CONFLUENCE 2026** International Conference on Cloud Computing, Data Science & Engineering.

---

## 🚀 Overview

Accurate forecasting of renewable energy (Solar/Wind) and Grid Load is critical for modern smart grids. This repository implements a robust pipeline for **12-hour ahead forecasting** using a 24-hour lookback window.

### Key Highlights:
- **Proposed Architecture:** Bahdanau-style Attention mechanism integrated with deep Bidirectional LSTMs.
- **Multi-Target Output:** Simultaneously predicts Solar PV Output, Wind Power Generation, and Grid Load.
- **Robust Validation:** Implements 5-Fold Rolling Origin Cross-Validation (Time-Series Split).
- **Hybrid Optimization:** Uses a custom `Hybrid Loss (MSE + 0.5 * MAE)` for improved stability against outliers.
- **Statistical Rigor:** Includes Paired T-Tests to confirm the significance of model improvements.

---

## 🏗️ Model Architecture

The core of this project is the **Attention-BiLSTM** model, designed to capture long-term dependencies and focus on critical timesteps in energy consumption patterns.

| Component | Description |
| :--- | :--- |
| **Input Layer** | 24-hour lookback window with multivariate features. |
| **BiLSTM Layers** | Two stacked Bidirectional LSTM layers (150 units each) for temporal feature extraction. |
| **Attention Mechanism** | Additive (Bahdanau) Attention to weigh the importance of specific past hours. |
| **Output Layer** | Dense layer with Reshape for 12-hour multi-target forecasting. |

---

## 📊 Datasets

The models were evaluated on two distinct datasets to ensure generalizability:

1.  **Local Microgrid Dataset:** Focused on individual renewable installation performance.
2.  **OPSD Germany Dataset:** High-granularity country-wide energy data from the Open Power System Data (Germany).

**Feature Engineering includes:**
- **Cyclical Encoding:** Transformation of `Hour of Day` and `Day of Week` using Sin/Cos transforms.
- **Temporal Lag:** Inclusion of lags (1h, 24h, 168h) to capture autocorrelation.
- **Normalization:** Feature scaling using `MinMaxScaler`.

---

## 📈 Performance & Results

### Evaluation Metrics:
- **RMSE / nRMSE:** Root Mean Square Error (Normalized).
- **MAE:** Mean Absolute Error.
- **MAPE / sMAPE:** Mean Absolute Percentage Error (Symmetric).
- **Stability:** Calculated via Standard Deviation across CV folds.

### Statistical Significance:
The project uses **SciPy-based Paired T-tests** to compare the Attention-BiLSTM against standard BiLSTM and Simple LSTM baselines, ensuring that performance gains are statistically significant (p < 0.05).

---

## 🛠️ Tech Stack

- **Core:** Python, TensorFlow, Keras
- **Data:** Pandas, NumPy, Scikit-Learn
- **Stats:** SciPy (Statistical Tests)
- **Environment:** Jupyter Notebook / Google Colab (GPU Accelerate T4 supported)

---

## ⚙️ Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/energy-forecast-attention-bilstm.git
   cd energy-forecast-attention-bilstm
   ```

2. **Install Dependencies:**
   ```bash
   pip install tensorflow pandas numpy scikit-learn scipy matplotlib
   ```

3. **Run the Notebook:**
   Open `AttentionBiLSTM_Forecasting.ipynb` in Jupyter or Colab and run all cells. Ensure your datasets (`Renewable_energy_dataset.csv`, `time_series_60min_singleindex.csv`) are placed in the root directory.

---

## 📬 Contact & Portfolio

**Deepu Guggilla**
- **GitHub:** [github.com/GUGGILLADEEPU](https://github.com/GUGGILLADEEPU)
- **LinkedIn:** [linkedin.com/in/deepu-guggilla](https://www.linkedin.com/in/deepu-guggilla/)
- **Email:** [deepuqwert1234@gmail.com](mailto:deepuqwert1234@gmail.com)

---

> [!TIP]
> This project is part of a research initiative to improve the reliability of renewable energy integration into small-scale microgrids.
