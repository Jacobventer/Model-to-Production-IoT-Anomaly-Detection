# Training Data Description

This folder contains the simulated sensor data used to train the anomaly detection model.

## training_data.csv
The dataset consists of historical, simulated IoT sensor readings representing wind turbine components in a factory environment.

Each row corresponds to a single sensor measurement and includes:
- **timestamp** – UTC timestamp of the sensor reading
- **machine_id** – Identifier of the wind turbine (e.g. WT-01, WT-02, WT-03)
- **temperature** – Temperature measurement in degrees Celsius
- **humidity** – Relative humidity percentage
- **sound** – Sound level in decibels (dB)

## Data Generation
The data was generated using a Python-based sensor simulator designed to approximate realistic operating conditions based on:
- Academic and industry literature on wind turbine condition monitoring
- Practical domain knowledge from experienced factory and technical workers

Sensor values follow approximately normal distributions within expected operating ranges, with occasional deviations to simulate abnormal behaviour.

## Purpose
This dataset is used exclusively for **offline training** of the Isolation Forest anomaly detection model. No labels as it is unsupervised learning

## Notes
- The data is fully simulated and does not originate from real turbines
- No data cleaning was required due to controlled generation
- The dataset is intended for proof-of-concept 

