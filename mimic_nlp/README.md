# MIMIC-NLP: Natural Language Processing on MIMIC-III AMI Discharge Summaries

This project performs natural language processing (NLP) analysis on discharge summaries from patients diagnosed with Acute Myocardial Infarction (AMI) using the MIMIC-III clinical database.

## Overview

The project focuses on:
- Extracting AMI patient cohorts from MIMIC-III dataset
- Processing discharge summary texts using various NLP libraries
- Generating word embeddings and visualizations (t-SNE, UMAP)
- Comparing different NLP models for medical text processing

## Dependencies

The following Python packages are required:
- spacy==3.6.1
- scispacy==0.5.3
- medspacy
- gensim
- umap-learn
- pandas
- numpy
- scikit-learn
- matplotlib

## Setup

1. Download the MIMIC-III dataset from [PhysioNet](https://physionet.org/content/mimiciii/1.4/)
2. Update the `data_location` path in the notebook to point to your local MIMIC-III directory
3. Install required packages using pip:
   ```bash
   pip install -r requirements.txt  # or manually install the packages listed above
   ```
4. Run the Jupyter notebook `mimic_nlp.ipynb`

## Project Structure

- `mimic_nlp.ipynb`: Main Jupyter notebook containing the analysis
- `images/`: Contains visualization plots of embeddings
- `presentation/`: Contains the project presentation (PowerPoint)

## Key Components

1. **Data Extraction**: Filters MIMIC-III data for AMI patients (ICD-9 codes 410.xx)
2. **Text Processing**: Uses multiple NLP libraries:
   - spaCy (general-purpose)
   - SciSpaCy (biomedical)
   - MedSpaCy (medical)
3. **Embeddings**: Generates Word2Vec embeddings
4. **Visualization**: Dimensionality reduction using t-SNE and UMAP

## Results

The project generates various plots comparing different NLP models' performance on medical text embeddings, saved in the `images/` folder.

## Presentation

A detailed presentation of the findings is available in `presentation/MIMIC NLP Presentation.pptx`.

## Note

Due to the large size of the MIMIC-III dataset, ensure you have sufficient storage and processing power. The dataset requires proper access credentials from PhysioNet.