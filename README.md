# ✈️ Fleet Engine Health Analytics: Predictive Maintenance for Turbofan Engines

## Project Overview

Predictive maintenance plays a critical role in aerospace systems, where unexpected engine failures can lead to significant operational costs, downtime, and safety risks. This project analyzes NASA's CMAPSS turbofan engine dataset to build an end-to-end predictive maintenance framework capable of monitoring engine health, estimating Remaining Useful Life (RUL), and identifying abnormal degradation patterns before failure occurs.

Using multivariate sensor data collected throughout an engine's lifecycle, the project transforms raw measurements into actionable maintenance insights through feature engineering, machine learning, and anomaly detection techniques.

The resulting framework demonstrates how data-driven approaches can support condition-based maintenance strategies and improve fleet-level asset management.

---

## Objectives

* Analyze multivariate sensor data from a fleet of turbofan engines
* Identify informative sensors and remove redundant signals
* Engineer meaningful features that capture engine degradation
* Develop interpretable health indicators for continuous monitoring
* Predict Remaining Useful Life (RUL) using machine learning models
* Detect abnormal engine behavior using unsupervised anomaly detection
* Visualize degradation trends at both engine and fleet levels

---

## Dataset

### Source

NASA CMAPSS Turbofan Engine Degradation Simulation Dataset

### Subset Used

FD001

### Dataset Characteristics

* Single operating condition
* Single fault mode
* High Pressure Compressor (HPC) degradation
* Multiple engines observed throughout their lifecycle
* Multivariate sensor measurements recorded at every operational cycle

Each engine begins in a healthy state and operates until failure, making the dataset well-suited for predictive maintenance and Remaining Useful Life modeling.

---

## Project Workflow

```text
Raw Sensor Data
        ↓
Data Cleaning & Validation
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Health Score Generation
        ↓
RUL Prediction
        ↓
Anomaly Detection
        ↓
Maintenance Insights
```

---

## Methodology

### 1. Data Cleaning & Validation

* Loaded raw engine sensor measurements
* Assigned meaningful column names
* Validated engine identifiers and operational cycles
* Removed redundant and empty columns
* Verified dataset consistency across the fleet

### 2. Exploratory Data Analysis (EDA)

* Examined engine lifespan variability
* Visualized sensor behavior across operational cycles
* Analyzed degradation patterns over time
* Calculated sensor variance to identify informative signals
* Compared degradation trajectories across multiple engines

### 3. Feature Engineering

To improve model performance and interpretability:

* Removed low-variance sensors
* Applied z-score normalization
* Generated rolling-window sensor averages
* Reduced sensor noise while preserving degradation trends
* Created a composite Engine Health Score to represent overall engine condition

### 4. Engine Health Monitoring

Health indicators were visualized at multiple levels:

* Individual engine degradation trajectories
* Fleet-wide health score distributions
* Comparative health progression across engines
* Longitudinal degradation trends

These analyses reveal significant variability in degradation behavior, highlighting the importance of predictive maintenance strategies tailored to individual assets.

### 5. Remaining Useful Life (RUL) Prediction

A machine learning pipeline was developed to estimate the number of operational cycles remaining before engine failure.

Key steps included:

* Generating RUL labels from engine failure cycles
* Performing engine-wise train/test splitting to prevent data leakage
* Training a Random Forest Regression model
* Evaluating predictive performance using MAE and RMSE
* Comparing predicted and actual RUL trajectories

The model successfully captures degradation trends and provides useful failure horizon estimates for maintenance planning.

### 6. Anomaly Detection

To identify abnormal engine behavior:

* Applied Isolation Forest on engineered sensor features
* Detected unusual degradation patterns
* Visualized anomalies alongside engine health trajectories
* Generated early warning indicators prior to failure

Anomaly detection complements RUL prediction by providing an additional layer of maintenance intelligence.

---

## Key Results

* Generated interpretable engine health trajectories
* Successfully predicted Remaining Useful Life using machine learning
* Detected abnormal operating behavior during advanced degradation stages
* Demonstrated variability in degradation patterns across the fleet
* Showed how sensor-driven analytics can support condition-based maintenance decisions

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Random Forest Regression
* Isolation Forest
* Time Series Analysis

---

## Repository Structure

```text
fleet-engine-health-analytics/
│
├── 01_data_exploration.ipynb
├── data/
├── images/
├── README.md
└── requirements.txt
```

---

## How to Run

### Clone the Repository

```bash
git clone https://github.com/yourusername/fleet-engine-health-analytics.git
cd fleet-engine-health-analytics
```

### Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate
```

### Install Dependencies

```bash
pip install pandas numpy matplotlib scikit-learn
```

### Launch the Notebook

```bash
jupyter notebook 01_data_exploration.ipynb
```

---

## Future Improvements

* Extend analysis to FD002–FD004 operating conditions
* Compare additional machine learning models (XGBoost, LightGBM)
* Implement deep learning approaches such as LSTM and GRU networks
* Add uncertainty estimation for RUL predictions
* Develop an interactive dashboard for fleet monitoring
* Simulate real-time maintenance alerts and decision support systems

---

## Key Takeaway

This project demonstrates how raw turbofan engine sensor data can be transformed into actionable maintenance intelligence through data analytics and machine learning. By combining health monitoring, Remaining Useful Life prediction, and anomaly detection within a unified framework, the project illustrates practical techniques used in modern predictive maintenance systems across aerospace and industrial applications.


