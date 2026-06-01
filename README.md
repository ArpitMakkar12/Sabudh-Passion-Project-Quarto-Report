# ⚡ EV Charging Infrastructure Optimization

> A Data-Driven Approach using XGBoost and Multi-Criteria Decision Making (MCDM)

[![Quarto](https://img.shields.io/badge/Built%20with-Quarto-blue?logo=quarto)](https://quarto.org/)
[![Python](https://img.shields.io/badge/Python-3.10%2B-yellow?logo=python)](https://www.python.org/)
[![XGBoost](https://img.shields.io/badge/Model-XGBoost-orange)](https://xgboost.readthedocs.io/)
[![Live Report](https://img.shields.io/badge/Live%20Report-View%20Here-green)](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/)
[![License: MIT](https://img.shields.io/badge/License-MIT-lightgrey)](LICENSE)

---

## 📖 About

This repository contains the **Sabudh Major Passion-Project** report for *"Data-Driven Optimization of EV Charging Infrastructure."* The project applies machine learning and geospatial analysis to identify the **top 300 optimal locations** for electric vehicle (EV) charging stations in an urban environment.

The report is built as a multi-chapter **Quarto Book** and is deployed on GitHub Pages.

🔗 **[Read the Full Report →](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/)**

---

## 🚗 Problem Statement

The rapid electrification of transportation is a global sustainability priority — yet **range anxiety** and the absence of well-placed charging infrastructure remain the biggest barriers to EV adoption. Traditional site-selection methods lack granular, data-driven insights. This project builds a scalable, reproducible framework that quantifies charging demand and recommends optimal station locations for urban planners and stakeholders.

---

## ✨ Key Highlights

- 📍 **Top 300 Priority Locations** identified and ranked by a composite demand-suitability score
- 🤖 **XGBoost Regressor** (R² = 0.88, RMSE = 42.1) outperformed Linear Regression and Random Forest
- 🗺️ **Interactive Heatmap** of recommended charging station locations ([view here](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/Enhanced_EV_Map.html))
- 🔢 **MCDM Layer** integrates raw ML predictions with real-world suitability constraints
- 📊 Comprehensive EDA with correlation heatmaps, feature importance, and distribution analysis

---

## 📚 Report Structure

| Chapter | Description |
|---|---|
| [Preface](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/preface.html) | Project background and acknowledgments |
| [Abstract](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/abstract.html) | Summary of the problem, approach, and findings |
| [1 · Introduction](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/intro.html) | Motivation, objectives, and study area |
| [2 · Pre-Processing & EDA](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/eda.html) | Dataset collection, cleaning, feature engineering |
| [3 · Methodology](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/methodology.html) | Model selection, training pipeline, MCDM design |
| [4 · Results](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/results.html) | Performance metrics, visualizations, sensitivity analysis |
| [5 · Conclusion](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/conclusion.html) | Summary, limitations, and future directions |
| [References](https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/chapters/references.html) | Academic citations |

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Report Framework** | [Quarto](https://quarto.org/) (Book format) |
| **Language** | Python 3.10+ |
| **ML Model** | XGBoost (`XGBRegressor`) |
| **Data Manipulation** | Pandas, NumPy |
| **Geospatial Data** | OpenStreetMap (OSM) via `osmnx` |
| **Model Evaluation** | Scikit-Learn |
| **Visualization** | Matplotlib, Seaborn, Folium (interactive maps) |
| **Dev Environment** | VS Code + Jupyter Notebook |
| **Hosting** | GitHub Pages |

---

## 🧠 Methodology Overview

The pipeline follows three stages:

```
Raw Geospatial Data (OSM, Traffic, POI, Demographics)
        ↓
  Feature Engineering (6 key features via RFE)
        ↓
  XGBoost Regressor → Predicted Demand Score
        ↓
  MCDM Layer (weighted suitability scoring)
        ↓
  Top 300 Priority Locations (ranked & mapped)
```

**6 Input Features used for prediction:**
- `land_use_entropy` — measure of mixed-use development
- `poi_density_commercial` — density of commercial points of interest
- `poi_density_residential` — density of residential points of interest
- `road_density_primary` — connectivity via primary roads
- `urban_centrality_score` — proximity to urban core
- `mixed_use_index` — composite land-use diversity score

---

## 📊 Model Performance

| Model | RMSE ↓ | R² ↑ | Training Time |
|---|---|---|---|
| Linear Regression | 145.2 | 0.42 | 0.5s |
| Random Forest | 89.4 | 0.76 | 12.3s |
| **XGBoost (Final)** | **42.1** | **0.88** | **4.1s** |

XGBoost was selected as the final model due to its superior accuracy, built-in regularization, and efficient handling of sparse geospatial grid data.

---

## 🗂️ Repository Structure

```
Sabudh-Passion-Project-Quarto-Report/
│
├── _quarto.yml              # Quarto book configuration
├── index.qmd                # Welcome / landing page
│
├── chapters/                # Report chapters (Quarto Markdown)
│   ├── preface.qmd
│   ├── abstract.qmd
│   ├── intro.qmd
│   ├── eda.qmd
│   ├── methodology.qmd
│   ├── results.qmd
│   ├── conclusion.qmd
│   └── references.qmd
│
├── img/                     # Figures and visualizations
│   ├── Model_Comparison.png
│   ├── Top_300_Points_Map.png
│   ├── Correlation_Heatmap.png
│   ├── Key_Features_Histogram.png
│   ├── Pipeline_Flowchart.png
│   └── ...
│
└── docs/                    # Rendered HTML output (GitHub Pages)
```

> **Note:** The Python notebooks/scripts used for data processing and model training may be maintained in a separate repository. See the report for full implementation details.

---

## 🚀 Running the Report Locally

To render the Quarto report on your machine:

**Prerequisites:**
- [Quarto CLI](https://quarto.org/docs/get-started/) (v1.8+)
- Python 3.10+ with required packages

**Steps:**

```bash
# 1. Clone the repository
git clone https://github.com/ArpitMakkar12/Sabudh-Passion-Project-Quarto-Report.git
cd Sabudh-Passion-Project-Quarto-Report

# 2. Install Python dependencies (if running code chunks)
pip install xgboost scikit-learn pandas numpy matplotlib seaborn

# 3. Render the Quarto book
quarto render

# 4. Preview locally
quarto preview
```

The rendered report will be available at `http://localhost:4321` (or similar).

---

## 👥 Authors

This project was submitted in partial fulfillment of the **Sabudh Major Passion-Project** requirements.

| Name | Role |
|---|---|
| **Arpit Makkar** | Lead Author |
| **Sarvagya Sharma** | Co-Author |
| **Abhinav Jain** | Co-Author |
| **Shashwat Shukla** | Co-Author |

*Supervised / Mentored by Dr. Sukhjit Singh*

---

## 📄 Citation

If you reference this work, please cite it as:

```
Makkar, A., Sharma, S., Jain, A., & Shukla, S. (2025).
Data-Driven Optimization for EV Charging Infrastructure.
Sabudh Major Passion-Project Report.
https://arpitmakkar12.github.io/Sabudh-Passion-Project-Quarto-Report/
```

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

*Built with [Quarto](https://quarto.org/) · Courtesy Dr. Sukhjit Singh*
