# 🚕 NYC Taxi Trip Duration Prediction 

This repository contains a complete **Exploratory Data Analysis (EDA)** and **Regression Modeling** workflow for predicting taxi trip duration in New York City.  
This project explores how trip duration is influenced by spatial coordinates, time, and passenger attributes.

---

## 🧩 Objectives
- Explore and clean raw NYC taxi trip data.
- Detect outliers and normalize variables.
- Discover relationships through heatmaps and correlations.
- Build regression models to predict `trip_duration`.
- Engineer new features (distance, month, weekend, etc.) to improve accuracy.
- Visualize passenger behavior and pickup density on NYC maps.

---

## 🧠 Dataset Details

**Source:** Kaggle – [NYC Taxi Trip Duration](https://www.kaggle.com/competitions/nyc-taxi-trip-duration)

| Attribute | Description |
|------------|-------------|
| `id` | Unique trip identifier |
| `vendor_id` | Taxi vendor code |
| `pickup_datetime`, `dropoff_datetime` | Start and end time of trip |
| `passenger_count` | Number of passengers |
| `pickup_longitude`, `pickup_latitude` | GPS coordinates of pickup |
| `dropoff_longitude`, `dropoff_latitude` | GPS coordinates of dropoff |
| `store_and_fwd_flag` | Whether trip data was stored before sending |
| `trip_duration` | Target variable (in seconds) |

**Rows:** 1.45 million  
---

## 🧮 Workflow Summary

### 🧱 1️⃣ Data Preprocessing
- Convert date/time columns to `datetime` format.
- Check for missing values (none found).
- Normalize `trip_duration` using **MinMaxScaler**.
- Detect outliers using **Seaborn boxplots**.

### 🔍 2️⃣ Relationship Discovery
- Correlation heatmap and pairplot to find variable dependencies.
- Passenger frequency analysis.
- Morning vs Evening average trip duration analysis.

### 📊 3️⃣ Regression Model 1
- Built with features: `vendor_id`, `pickup_longitude`, `pickup_latitude`, `dropoff_latitude`.
- Evaluated via `statsmodels.OLS`.

### ⚙️ 4️⃣ Feature Engineering
- Created new predictors:
  - `pickup_hour`, `pickup_dayofweek`, `pickup_month`, `pickup_is_weekend`
  - `distance` (computed using `geopy.geodesic`)
- Re-trained regression → R² ≈ 0.023 (showing improvement).

### 🗺️ 5️⃣ Visualization Highlights
- Histograms for passenger count, pickup months, weekends.
- Scatter plots: distance vs trip duration, month vs duration.
- Interactive **Folium** map of sampled pickup points.

---

## 🧰 Tools & Libraries
| Category | Libraries |
|-----------|------------|
| Data Handling | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn`, `folium` |
| Modeling | `statsmodels`, `sklearn` |
| Geospatial | `geopy` |
| Environment | **Google Colab** + Google Drive |

