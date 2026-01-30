# Model-to-Production-IoT-Anomaly-Detection
This project is a proof of concept that integrates a ML pipeline for anomaly detection using IoT sensor data in a factory. The sensors measure temperature, humidity and sound volume of wind turbines during production.

## Overview
In this project an end-to-end machine learning pipeline is implemented for anomaly detection in wind turbine components using simulated IoT sensor data.
It was developed as part of the *From Model to Production* course, part of my BSc Data Science degree. The focus is on practical ML engineering concepts rather than model complexity.

An unsupervised anomaly detection model is trained and the system simulates a continous sensor stream. Predictions are made via a RESTful API. The results are loged for evaluation and monitoring.

## Problem Statement
Wind turbine components operate under varying environmental and mechanical conditions.  
Early detection of abnormal behaviour in temperature, humidity, and sound levels can prevent costly downtime.

Challenges addressed:
- Lack of labeled failure data
- Highly imbalanced anomaly events
- Unknown failure patterns

To address these challenges, an **unsupervised anomaly detection approach** was chosen.

## Repository Structure
```bash
project/
│
├── data/
│   ├── training_data.csv        #Historical simulated data for model training
│   └── README.md                #Brief description of data set
│
├── models/
│   └── isolation_forest.pkl     #Offline-trained model
│
├── logs/
│   └── predictions_log.csv      #Live inference results from API
│
├── src/
│   ├── generate_training_data.py    #Generates sensor data to train model
│   ├── train_model.py               #Trains Isolation Forest and saves model
│   ├── model.py                     #Loads model and performs inference
│   ├── app.py                       #Setup and run Flask REST API for predictions
│   ├── sensor_simulator_live.py     #Simulates live sensor data stream
│   ├── rule_based_validator.py      #Rule-based check
│
├── evaluation/
│   ├── model_evaluation.py          #Offline evaluation & visualization
│
├── dashboard/
│   └── dashboard_mock.py            #Mock BI-style dashboard (static)
│
├── requirements.txt                 #Python dependencies
└── README.md                        #Project overview & run instructions

```

## System Architecture
The system consists of the following components:

1. **Sensor Simulator** – Generates continuous, realistic sensor data
2. **Data Logging Layer** – Stores predictions and sensor readings
3. **Model Training Module** – Trains an Isolation Forest offline
4. **Inference API** – Exposes anomaly predictions via REST
5. **Evaluation & Monitoring** – Analyses logged predictions

## Conceptual BI Dashboard (Mock)

The following image illustrates a conceptual Business Intelligence (BI) dashboard that could be used by factory managers to monitor system health at a glance.

The dashboard highlights:
- Overall system status (normal vs anomaly detected)
- Affected machine and sensor type
- Recent anomaly indicators for temperature, humidity, and sound

This dashboard is a **static mock-up** and serves to demonstrate how the API outputs and logged predictions could be consumed by a real BI tool such as Power BI, Tableau, or Grafana.

![Conceptual BI Dashboard](dashboard/Conceptual_BI_Dashboard.png) 


## Machine Learning Model
- **Model:** Isolation Forest
- **Type:** Unsupervised anomaly detection
- **Features:** Temperature, Humidity, Sound
- **Training:** Offline using simulated sensor data
- **Inference:** Real-time via REST API


## How to Run the Project

### 1. Install dependencies
```pip install -r requirements.txt```
### 2. Generate training data
```python src/generate_training_data.py```
### 3. Train the model
```python src/train_model.py```
### 4. Start the API
```python src/app.py```
### 5. Start live sensor simulation
```python src/sensor_simulator_live.py```
### 6. Evaluate results
```python evaluation/model_evaluation.py```


## Results summary
- Anomalies represent approximately 3% of all readings
- Anomaly rates are balanced across machines
- Distributions align with expected physical behaviour
- Logged predictions allow post-hoc analysis and monitoring

## Limitations
- Data is simulated and not collected from real turbines
- Global model (not machine-specific)
- Dashboard is a mock-up, not a live BI integration
- Limited hyperparameter tuning

## Conclusion
This project demonstrates a complete model-to-production pipeline including:
- Domain-informed data generation
- Offline model training
- Online inference via REST API
- Logging and evaluation

The focus is on realistic engineering decisions and system design rather than maximizing model accuracy.

## Author
Jaco Venter

BSc Data Science student at International University of Applied Scinece (Germany)
#### https://www.linkedin.com/in/jaco-venter-45502a162/

## License
This project is for academic purposes only as part of the Data Science degree at IU International University of Applied Science
