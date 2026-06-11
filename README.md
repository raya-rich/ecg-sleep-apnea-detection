# ECG Sleep Apnea Detection

Machine learning project for detecting obstructive sleep apnea using ECG signals and Heart Rate Variability (HRV) analysis.

## Project Overview

This project automatically detects sleep apnea from single-channel ECG signals using HRV features extracted during sleep. The autonomic nervous system responds to apnea events, causing irregular heartbeat patterns that can be captured through HRV analysis.

## Dataset

Download and extract the dataset:
- `dataset_train.7z` - Training data (624 samples: 331 normal, 293 apnea)
- `dataset_test.7z` - Test data (156 samples: 81 normal, 75 apnea)
- Sampling rate: 100 Hz

Extract both 7z files before running the notebook.

## Pipeline

1. Load ECG data (normal vs apnea)
2. Clean ECG + Detect R-peaks
3. Extract HRV features using Neurokit2
4. Feature selection (SelectKBest - top 20 features)
5. Train Gradient Boosting classifier
6. Evaluate performance

## Results

- **Best Model:** Gradient Boosting Classifier
- **Final Accuracy:** 78.21%
- **Top Feature:** HRV_VLF (0.23 importance)

### Top 5 Most Important Features
1. HRV_VLF - Very slow changes in heart rate linked to breathing
2. HRV_MFDFA_alpha2_Peak - Heartbeat pattern complexity
3. HRV_HTI - Shape of heartbeat timing distribution
4. HRV_MFDFA_alpha2_Mean - Average complexity of heartbeat
5. HRV_CD - Unpredictability of heartbeat pattern

## Requirements
numpy

pandas

neurokit2

scikit-learn

matplotlib

seaborn

## Usage

Run `ecg-sleep-apnea-detection.ipynb` in Jupyter Notebook after extracting the dataset.
