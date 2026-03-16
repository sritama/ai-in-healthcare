## Healthcare ML & DL Tutorial (MIMIC-III)

This repository contains a hands‑on tutorial for applying **machine learning and basic deep learning concepts to critical care data** from the **MIMIC‑III clinical database**. The main workflow is implemented in the `healthcare_ml_dl.ipynb` Jupyter notebook and is complemented by a slide deck (PowerPoint) in the same directory that provides conceptual background and teaching material.

The tutorial walks through:
- **Data loading** from MIMIC‑III tables (patients, admissions, ICU stays, chart events, lab events, notes).
- **Feature engineering** using demographics, admission metadata, vital signs, and laboratory values.
- **Exploratory analysis & visualization** of outcomes such as hospital mortality and ICU length of stay.
- **Predictive modeling** with classical ML models (e.g., Logistic Regression, Random Forest) and text features (TF‑IDF) for clinical notes.
- **Model evaluation** with metrics such as ROC curves and AUC.

---

### 1. Project Structure

- `healthcare_ml_dl.ipynb`  
  End‑to‑end notebook for data preparation, feature extraction, visualization, and modeling on MIMIC‑III.

- `README.md`  
  Project overview, setup instructions, and usage guide (this file).

- `images/`  
  Folder created by the notebook to store exported figures, such as:
  - `hospital_mortality_bar_chart.png`
  - ICU length‑of‑stay histograms and other plots generated during EDA.

- `*.pptx` (slide deck)  
  Lecture slides summarizing the motivation, dataset, methods, and key results used for teaching.

> **Note**: The raw MIMIC‑III data files (e.g., `PATIENTS.csv.gz`, `ADMISSIONS.csv.gz`, `ICUSTAYS.csv.gz`, `CHARTEVENTS.csv.gz`, `LABEVENTS.csv.gz`, `NOTEEVENTS.csv.gz`) are **not** included in this repository and must be obtained separately from PhysioNet under the appropriate data use agreements.

---

### 2. Prerequisites

- **Python** 3.8+ (3.10 recommended)
- A local copy of the **MIMIC‑III v1.4** dataset in a directory you control
- Open the Jupyter notebook in Jupyter Lab or local IDE (I used Visual Studio Code)
- Install the required Python packages as mentioned in the slides (or you can install them as you run the Jupyter notebook cell by cell).

The notebook assumes that the MIMIC‑III CSV files are available under:

```python
data_location = "../../Dataset/mimic-iii-clinical-database-1.4/"
```

You can modify this path near the top of the notebook to match where you have stored the dataset.

---

### 3. Running the Notebook

1. **Launch Jupyter** from this directory:

   ```bash
   jupyter lab
   ```

   or

   ```bash
   jupyter notebook
   ```

2. Open `healthcare_ml_dl.ipynb`.

3. In the **“Load MIMIC Tables”** section, confirm that `data_location` points to your local MIMIC‑III folder.

4. Run the notebook **top‑to‑bottom**, or execute it section‑by‑section:
   - Import libraries
   - Load MIMIC tables
   - Build vitals and lab feature tables
   - Merge tables and construct the modeling dataframe
   - Visualize mortality and ICU length of stay
   - Train and evaluate ML models

The notebook will generate figures and save them into the `images/` directory (e.g., `hospital_mortality_bar_chart.png`) for later use in reports or slides.

---

### 4. Data & Privacy Considerations

- Access to MIMIC‑III data requires **completion of the PhysioNet credentialing and data use agreement**. See the official project page for details.
- **Do not commit or share raw MIMIC‑III data** in any public repository.
- When sharing results, ensure that no identifiable patient information is exposed and follow your institutional guidelines and IRB policies.

---

### 5. Using the Slide Deck

The PowerPoint slide deck in this directory is intended to accompany the notebook for teaching purposes. It typically includes:

- Background on AI and ML in healthcare
- Overview of the MIMIC‑III dataset and ICU context
- Explanation of the feature engineering and modeling steps used in the notebook
- Visualizations and example results exported from `images/`

You can update the slides to incorporate additional plots or models you add to the notebook.

---

### 6. Extending the Tutorial

Ideas for extending this tutorial include:

- Adding **more advanced models**, including gradient boosting or deep neural networks.
- Incorporating **time‑series features** (e.g., trajectories of vitals and labs rather than simple averages).
- Exploring **natural language processing** on clinical notes using more advanced embeddings or transformer‑based models.
- Performing **hyperparameter tuning**, calibration, and fairness analysis across patient subgroups.

Contributions and adaptations for teaching or research are welcome—feel free to extend this tutorial to fit your own healthcare ML workflows.

