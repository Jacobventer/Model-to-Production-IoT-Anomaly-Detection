# Model-to-Production-IoT-Anomaly-Detection
This propject is a proof of concept that integrates a ML pipeline for anomaly detection from IoT devices in a factory. The sensors measure temperature, humidity and sound volume of wind turbines. in production

## Overview

## Repository Structure
```bash
project/
│
├── data/
│   ├── training_data.csv        # Historical simulated data used for model training
│   └── README.md                # Brief description of how data was generated
│
├── models/
│   └── isolation_forest.pkl     # Trained ML model (offline-trained)
│
├── logs/
│   └── predictions_log.csv      # Live inference results from API
│
├── src/
│   ├── generate_training_data.py    # Generates historical sensor data (offline)
│   ├── train_model.py               # Trains Isolation Forest and saves model
│   ├── model.py                     # Loads model and performs inference
│   ├── app.py                       # Flask REST API for predictions
│   ├── sensor_simulator_live.py     # Simulates live sensor data stream
│   ├── rule_based_validator.py      # Optional rule-based sanity check
│
├── evaluation/
│   ├── model_evaluation.py          # Offline evaluation & visualization
│
├── dashboard/
│   └── dashboard_mock.py            # Mock BI-style dashboard (static)
│
├── requirements.txt                 # Python dependencies
└── README.md                        # Project overview & run instructions


```



## License
This project is for academic purposes only as part of the Data Science degree at IU International University of Applied Science
