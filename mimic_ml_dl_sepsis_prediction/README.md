# MIMIC-ML-DL-Sepsis-Prediction: Early Sepsis Prediction Using Deep Learning

This project implements an end-to-end time-series deep learning pipeline for early sepsis prediction using the MIMIC-III Clinical Database. The goal is to predict sepsis onset 12 hours before it occurs using 48 hours of preceding ICU vital signs and lab results.

## Overview

Sepsis is a life-threatening organ dysfunction caused by a dysregulated response to infection. Every hour of delayed treatment increases mortality by approximately 7%. This project develops machine learning models to identify sepsis risk early, enabling timely clinical intervention.

## Models Compared

| Model | Type | Input |
|---|---|---|
| **XGBoost** | Gradient Boosted Trees (Baseline) | Aggregate statistics over 48h window |
| **LSTM** | Recurrent Deep Learning | Full 48-timestep sequence (48 × 80 features) |
| **Transformer** | Self-Attention Deep Learning | Full 48-timestep sequence with CLS token |

## Key Design Decisions

- **Sepsis-3 labelling**: Infection (antibiotic proxy) + organ dysfunction (SOFA proxy)
- **Onset-only label**: Only the *first* timestep where criteria are met is marked positive
- **Patient-level train/test split**: Prevents data leakage from overlapping sliding windows
- **Apple M3 MPS acceleration**: Enables GPU-speed training on local hardware

## Dataset

**MIMIC-III (Medical Information Mart for Intensive Care III)**
- De-identified health data from 40,000+ ICU patients (2001-2012)
- Tables used: PATIENTS, ADMISSIONS, ICUSTAYS, PRESCRIPTIONS, CHARTEVENTS, LABEVENTS
- Focus: ICU vital signs and lab results for sepsis prediction

## Dependencies

```
pandas
numpy
matplotlib
scikit-learn
xgboost
torch (PyTorch)
```

## Setup

1. **Get MIMIC-III Dataset**:
   - Download from [PhysioNet](https://physionet.org/content/mimiciii/1.4/)
   - Requires credentialed access

2. **Install Dependencies**:
   ```bash
   pip install pandas numpy matplotlib scikit-learn xgboost torch
   ```

3. **Update Data Path**:
   - Modify `data_path` in the notebook to point to your local MIMIC-III directory

4. **Run the Notebook**:
   - Execute `mimic_sepsis_prediction_submission.ipynb`
   - Results and visualizations will be saved in the `images/` folder

## Methodology

### Data Processing
- Extract 48-hour windows of vital signs and lab data
- Handle missing values and irregular sampling
- Create sepsis labels using Sepsis-3 criteria

### Model Training
- Patient-level cross-validation to prevent data leakage
- Handle class imbalance with oversampling
- Optimize thresholds for F1 score maximization

### Evaluation Metrics
- **AUC-ROC**: Ranking ability for discriminative power
- **AUPRC**: Precision-Recall tradeoff for imbalanced data
- **F1 Score**: Harmonic mean of precision and recall at optimal threshold

## Results

The project compares the performance of traditional ML (XGBoost) against deep learning approaches (LSTM, Transformer) for time-series sepsis prediction. Results include:

- Model performance comparisons
- ROC curves and precision-recall curves
- Confusion matrices
- Training loss curves
- Attention heatmaps (for Transformer model)
- Risk-over-time visualizations

## Project Structure

- `mimic_sepsis_prediction_submission.ipynb`: Main analysis notebook
- `images/`: Contains all visualization plots and charts
  - `model_performance_bar.png`: Model comparison results
  - `roc_curve_comparison.png`: ROC curves for all models
  - `precision_recall_curve.png`: Precision-recall analysis
  - `confusion_matrix_for_best_method_commented.png`: Confusion matrix
  - `attention_heatmap.png`: Transformer attention visualization
  - `training_loss_curves.png`: Training progress
  - `sepsis_risk_over_time.png`: Risk prediction over time
- `presentation/`: Project presentation slides

## Clinical Impact

Early sepsis detection can significantly improve patient outcomes by enabling:
- Timely antibiotic administration
- Appropriate fluid resuscitation
- Organ support measures
- Reduced mortality and length of stay

## Notes

- Requires MIMIC-III dataset access (PhysioNet credentials)
- Notebook includes Apple M3 MPS GPU acceleration for faster training
- Handles imbalanced data with positive class oversampling
- Uses patient-level splits to prevent temporal data leakage

## Citation

This work uses the MIMIC-III dataset. Please cite:
```
Johnson, A. E. W., et al. (2016). MIMIC-III, a freely accessible critical care database.
Scientific Data, 3:160035.
```