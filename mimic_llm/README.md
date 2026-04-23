# MIMIC-LLM: Large Language Models for ICU Outcome Prediction

This project demonstrates the application of Large Language Models (LLMs) for predicting ICU patient outcomes using the MIMIC-III clinical database. It compares various prompting strategies and evaluates their performance on mortality risk and length-of-stay prediction tasks.

## Overview

The project explores how LLMs can reason over structured Electronic Health Record (EHR) data to make clinical predictions without requiring expensive model fine-tuning. It implements and compares multiple prompting techniques using GPT-4o as the primary model and GPT-3.5-turbo as a baseline.

## Key Features

- **Zero-shot Learning**: Direct prediction without examples
- **Few-shot In-Context Learning (ICL)**: 1-shot and 3-shot learning
- **Chain-of-Thought (CoT)**: Step-by-step reasoning
- **Tree-of-Thoughts (ToT)**: Multi-path reasoning exploration
- **Self-Consistency**: Multiple reasoning paths with majority voting
- **Bonus Downstream Task**: Integration with traditional ML models

## Dataset

**MIMIC-III (Medical Information Mart for Intensive Care III)**
- De-identified health data from 40,000+ ICU patients (2001-2012)
- Tables used: ADMISSIONS, LABEVENTS, CHARTEVENTS, PRESCRIPTIONS
- Focus: ICU mortality risk and length-of-stay prediction

## Models

- **Primary**: GPT-4o
- **Baseline**: GPT-3.5-turbo

## Dependencies

```
openai
pandas
numpy
scikit-learn
matplotlib
seaborn
tabulate
tqdm
aiohttp
nest_asyncio
```

## Setup

1. **Get MIMIC-III Dataset**:
   - Download from [PhysioNet](https://physionet.org/content/mimiciii/1.4/)
   - Requires credentialed access

2. **Install Dependencies**:
   ```bash
   pip install openai pandas numpy scikit-learn matplotlib seaborn tabulate tqdm aiohttp nest_asyncio
   ```

3. **API Key**:
   - Obtain OpenAI API key
   - Update `OPENAI_API_KEY` in the notebook

4. **Run the Notebook**:
   - Execute `mimic_llm_with_mimic_III_dataset.ipynb`
   - Results will be saved in `csv_files/` and `images/`

## Project Structure

- `mimic_llm_with_mimic_III_dataset.ipynb`: Main analysis notebook
- `csv_files/`: Contains prediction results and evaluation metrics
  - `mimic_llm_results_all_methods.csv`: All prediction results
  - `mimic_llm_table1_metrics.csv`: Performance metrics summary
  - `mimic_llm_table3_judge_scores.csv`: Human evaluation scores
  - `mimic_llm_bonus_downstream_ml.csv`: Bonus ML task results
- `images/`: Visualization plots and charts
- `presentation/`: Project presentation slides

## Results Summary

The project evaluates LLM performance on two main tasks:

1. **Mortality Prediction**: Binary classification (survived/died)
2. **Length-of-Stay Prediction**: Multi-class classification (short/medium/long stay)

Key findings include performance comparisons across different prompting strategies, with Tree-of-Thoughts showing strong results for mortality prediction.

## Evaluation Metrics

- Accuracy, F1-Score, AUC
- Precision, Recall
- Confidence scores
- Human judge evaluations

## Visualizations

The `images/` folder contains various plots:
- Model performance comparisons
- Confusion matrices
- Precision-recall curves
- F1-score heatmaps
- Judge evaluation boxplots and radar charts

## Presentation

Detailed results and methodology are presented in `presentation/MIMIC_LLM_Presentation.pptx`.

## Notes

- Requires OpenAI API access and credits
- MIMIC-III dataset access requires PhysioNet credentials
- Notebook includes async API calls for efficient batch processing
- All results are cached in CSV files to avoid re-running expensive API calls

## Citation

This work uses the MIMIC-III dataset. Please cite:
```
Johnson, A. E. W., et al. (2016). MIMIC-III, a freely accessible critical care database.
Scientific Data, 3:160035.
```