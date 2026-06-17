
# ✈️ Fleet-Level Turbofan Engine Health Analytics & Predictive Maintenance
##  Project Overview

This project develops an end-to-end engine health analytics and predictive maintenance framework using NASA’s CMAPSS turbofan engine dataset. The goal is to transform raw multivariate sensor time-series data into interpretable health indicators, failure horizon predictions, and early anomaly warnings that support condition-based maintenance and fleet-level decision-making.

The project emphasizes data understanding, feature engineering, interpretability, and realistic model evaluation, aligning with real-world aerospace and industrial asset monitoring scenarios.

## Objectives

- Ingest and analyze raw time-series sensor data from a fleet of turbofan engines

- Identify informative sensors and remove non-contributing signals

- Construct interpretable engine health indicators over time

- Predict Remaining Useful Life (RUL) using regression modeling

- Detect abnormal degradation behavior using unsupervised anomaly detection

- Visualize degradation trends at both engine and fleet levels

## Dataset

- Source: NASA CMAPSS Turbofan Engine Degradation Dataset

- Subset Used: FD001

- Single operating condition

- Single fault mode (High Pressure Compressor degradation)

### Structure:

- Multiple engines (fleet-level)

- Multivariate sensor readings per operational cycle

- Engines run from healthy state to failure

- Each engine represents an independent degradation trajectory, making the dataset ideal for predictive maintenance and Remaining Useful Life modeling.

###  Methodology
#### Data Ingestion & Validation

-  Loaded raw sensor data and assigned meaningful column names

- Verified number of engines, cycle lengths, and data consistency

- Removed empty or redundant columns

#### Exploratory Data Analysis (EDA)

-  Analyzed cycles per engine to understand lifespan variability

- Visualized raw sensor behavior to observe degradation patterns

- Computed sensor variance across the fleet to identify informative sensors

#### Feature Engineering

- Removed low-variance sensors to reduce noise

- Applied z-score normalization to ensure consistent feature scaling

- Computed rolling mean features per engine to smooth sensor noise

- Constructed a composite engine health score representing overall condition

#### Health Monitoring & Visualization

- Engine-level degradation trends over time

- Fleet-level health score distribution

- Comparative health trajectories across multiple engines

- These visualizations reveal significant variability in degradation behavior across the fleet, motivating individualized maintenance strategies.

#### Remaining Useful Life (RUL) Modeling

- Derived RUL labels based on engine failure cycles

- Used an engine-wise train/test split to prevent data leakage

- Trained a Random Forest regression model on rolling sensor features

- Evaluated model performance using MAE and RMSE

- Visualized predicted vs actual RUL for individual engines

-  The model accurately tracks degradation trends and estimates failure horizons, particularly during late-life stages critical for maintenance planning.

#### Anomaly Detection

- Applied Isolation Forest on rolling sensor features

- Identified abnormal behavior during late-stage degradation

- Visualized anomalies overlaid on engine health trajectories

- Anomaly detection complements RUL prediction by providing early warning signals prior to failure.

### Key Results

- Clear, interpretable engine health trajectories

- Realistic RUL prediction with engine-wise generalization

- Anomalies detected primarily during severe degradation phases

- Demonstrated variability in degradation patterns across the fleet


### How to Run

- Clone the repository

- Create and activate a Python virtual environment

- Install required libraries:

          pip install pandas numpy matplotlib scikit-learn


- Open and run 01_data_exploration.ipynb

### Future Work

- Extend the framework to FD002–FD004 datasets with multiple operating conditions and fault modes

- Incorporate sequence-based deep learning models (LSTM/GRU)

- Add uncertainty estimation for RUL predictions

- Explore real-time monitoring and alerting simulations

### Key Takeaway

This project demonstrates how raw sensor data can be transformed into actionable maintenance intelligence, combining health monitoring, failure horizon prediction, and anomaly detection within a unified, interpretable framework suitable for real-world aerospace applications.

