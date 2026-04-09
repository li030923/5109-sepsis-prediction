# 5109-sepsis-prediction
# Early Sepsis Risk Prediction from ICU Time-Series Data

A reproducible machine learning pipeline for early sepsis risk prediction using hourly ICU time-series data from the PhysioNet/Computing in Cardiology Challenge 2019 dataset.

## Overview

Sepsis is a life-threatening condition in intensive care units (ICUs), and early identification is critical for timely intervention. This project develops and evaluates four machine learning models for hourly sepsis risk prediction:

- Logistic Regression
- Random Forest
- GRU
- LSTM

To improve temporal comparability across models, the pipeline aligns all models around a 12-hour temporal context:

- **Logistic Regression** and **Random Forest** are trained on **12-hour window-level engineered tabular features**
- **GRU** and **LSTM** are trained on **12-hour sliding raw hourly sequences**

The project evaluates both:

- **Discriminative performance**: AUROC, AUPRC, Sensitivity, Specificity, Precision, NPV, Accuracy
- **Clinical early warning utility**: Mean lead time and mean false alarms per patient under a strict sustained-alert definition

---

## Dataset

This study uses the **PhysioNet/Computing in Cardiology Challenge 2019 Sepsis Dataset** in hourly tabular format.

Each row represents one patient-hour observation and includes:

- `patient_id`
- `ICULOS` (ICU length of stay in hours)
- hourly physiological and laboratory measurements
- binary target variable `SepsisLabel`

> Note: The raw dataset is **not included** in this repository due to data usage restrictions. Please download it from the official PhysioNet source and place it in the appropriate local directory before running the pipeline.

---
