# 🇸🇬 Singapore HDB Resale Price Prediction: AI & Geospatial Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Random%20Forest-green)
![Status](https://img.shields.io/badge/Status-Completed-orange)

## 📖 Project Overview

This project aims to predict resale prices of Housing and Development Board (HDB) flats in Singapore using advanced Machine Learning techniques. Unlike standard regression tasks, this project heavily emphasizes **Geospatial Feature Engineering** and **Socio-Economic Analysis** to capture real-world market dynamics.

By integrating external geospatial data (MRT stations, Elite Schools, CBD coordinates), we uncover hidden value drivers in the Singapore property market, achieving a high predictive accuracy with a **Random Forest** model.

## 🚀 Key Features & Methodology

### 1. Advanced Geospatial Engineering
Instead of relying solely on flat attributes, we engineered location-based features using the Haversine formula:
*   **MRT Connectivity:** Calculated precise distance to the nearest of **150+ MRT/LRT stations**. Analysis revealed a non-linear "U-shaped" price trend relative to distance.
*   **The "School Premium":** Quantified the "Kiasu" effect by measuring distance to top-tier primary schools. Found a correlation of **-0.21**, stronger than transport proximity.


### 2. Market Dynamics & Economic Analysis
*   **Temporal Trends:** Identified a structural market break during the 2020 COVID-19 "Circuit Breaker," explaining the post-pandemic price surge.
*   **Lease Decay (Bala's Curve):** Visualized non-linear value depreciation, proving that older flats in mature estates retain value better than theoretical models suggest.
*   **Regional Clustering:** Used Geospatial Clustering (Lat/Long) to identify "High Value" vs. "Budget" zones based on Price Per Sqm, debunking the "Size vs. Location" paradox in towns like Punggol.

### 3. Automated Data Pipeline
*   Utilized `kagglehub` to automatically fetch and cache external coordinate datasets, eliminating manual downloads.
*   Implemented robust data merging strategies to map addresses to geolocation.

## 🧠 Model Performance

We benchmarked three algorithms. **Random Forest** outperformed others by effectively capturing the non-linear relationships inherent in geospatial and temporal data.

| Model | R² Score | RMSE ($) | Key Strength |
| :--- | :--- | :--- | :--- |
| **Random Forest** | **0.96** | **~35k** | Captures non-linear location premiums & lease decay curves. |
| Decision Tree | 0.92 | ~52k | Good interpretability but prone to overfitting. |
| Linear Regression | 0.66 | ~106k | Fails to capture complex spatial interactions. |

## 📂 Repository Structure

*   `HDB_Project_Notebook.ipynb`: The core analysis notebook containing data cleaning, feature engineering, modeling, and visualization.
*   `hdb_prices.csv`: (Placeholder) The dataset used for training.
*   `README.md`: Project documentation.

## 🛠️ Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/YOUR_USERNAME/hdb-price-prediction-ai.git
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn folium kagglehub
    ```
3.  **Run the Notebook:**
    Open `HDB_Project_Notebook.ipynb` in Jupyter or VS Code and run all cells. The external datasets will be downloaded automatically via the API.

## 📊 Visualizations Included
*   **Interactive Heatmaps:** Geospatial distribution of high vs. low price clusters.
*   **Regression Plots:** Lease decay analysis and Temporal trends.
*   **Boxplots:** Regional valuation comparisons and "1km School Limit" premiums.

---
*This project was developed as part of the CA6001 AI Algorithms Fundamentals & Application course.*
