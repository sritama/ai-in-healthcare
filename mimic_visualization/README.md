### MIMIC-III ICU Patient Visualization

This folder contains an exploratory data analysis and visualization notebook built on the MIMIC-III clinical database, along with a companion presentation. The goal is to visually summarize ICU patient demographics, admissions patterns, outcomes, and common medications.

### Contents

- **`MIMIC_Visualiazation.ipynb`**: Main Jupyter notebook that loads MIMIC-III tables and generates visualizations.
- **`Predicting_Hospital_Mortality_Using_ML_DL.pptx`** (in this folder): Slide deck that presents key plots and insights derived from the notebook in a talk-friendly format.

### Data & Prerequisites

- **Dataset**: MIMIC-III v1.4 clinical database from PhysioNet.
  - Official source: `https://physionet.org/content/mimiciii/1.4/`
  - Required tables (gzipped CSVs as used in the notebook):
    - `PATIENTS.csv.gz`
    - `ADMISSIONS.csv.gz`
    - `ICUSTAYS.csv.gz`
    - `PRESCRIPTIONS.csv.gz`
- **Local path configuration**:
  - In the notebook, the MIMIC-III root directory is referenced via:
    - `data_location = "../../Dataset/mimic-iii-clinical-database-1.4/"`
  - Adjust this path if your local folder structure is different, but keep the individual file names the same.

### Environment

The notebook assumes a standard scientific Python stack:

- **Python**: 3.8+ recommended
- **Core libraries**:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `plotly`

You can install these with:

```bash
pip install pandas numpy matplotlib seaborn plotly
```

### How to Run the Notebook

1. **Download MIMIC-III**  
   Obtain access and download the MIMIC-III v1.4 clinical database from PhysioNet, then unpack it into a local directory (or ensure the gzipped CSVs are available under the configured `data_location`).

2. **Open the notebook**  
   From the project root:
   ```bash
   cd mimic_visualization
   jupyter notebook MIMIC_Visualiazation.ipynb
   ```

3. **Configure the data path (if needed)**  
   - In the “Load Data Used In Visualization” section, update the `data_location` variable to point to your local MIMIC-III folder.

4. **Run cells in order**  
   - Execute the setup and data-loading cells first.
   - Then run each visualization section in sequence to reproduce the plots.

### Visualizations in the Notebook

The notebook builds a set of clinically oriented plots using the core MIMIC-III tables:

- **1. Population pyramid (Age × Gender)**  
  - Uses `PATIENTS` and derived age at admission.  
  - Visualizes male and female ICU admissions mirrored around the vertical axis across 5-year age bands.

- **2. Admission heatmap (Day × Hour)**  
  - Uses `ADMISSIONS` timestamps.  
  - Produces a heatmap of admission counts by day of week and hour, highlighting peak admission periods.

- **3. Mortality vs. Length of Stay**  
  - Combines `ADMISSIONS` and ICU stay information.  
  - Computes length of stay and an event flag (death vs. censored) to show how mortality relates to ICU duration.

- **4. Survival curve (Kaplan–Meier style)**  
  - Reuses the length-of-stay and event information to approximate survival curves over ICU stay duration.

- **5. Top medications administered in ICU**  
  - Merges `PRESCRIPTIONS` with `ICUSTAYS`.  
  - Normalizes medication names and counts the most frequently administered drugs during ICU stays.

- **6. ICU length of stay by ICU type**  
  - Uses `ICUSTAYS` to compare LOS distributions across different ICU units (e.g., MICU, SICU, CCU).

- **7. ICU length of stay vs. age**  
  - Merges `PATIENTS`, `ADMISSIONS`, and `ICUSTAYS`.  
  - Explores how ICU LOS varies with patient age.

Each section includes the data preparation steps (filtering, merging, feature engineering) followed by either static `matplotlib`/`seaborn` plots or interactive `plotly` visualizations.

### Using the Presentation

The PowerPoint file in this folder:

- Summarizes the main analyses from `MIMIC_Visualiazation.ipynb`.
- Is structured for talks or teaching sessions about:
  - ICU patient demographics in MIMIC-III  
  - Admission patterns over time  
  - Mortality, survival, and ICU length of stay  
  - Frequently used ICU medications

You can regenerate or update the figures in the slides by re-running the notebook, exporting updated plots, and replacing them in the `.pptx`.

### Folder Structure (this subproject)

- `MIMIC_Visualiazation.ipynb` – main EDA and visualization notebook.  
- `README.md` – this file.  
- `Predicting_Hospital_Mortality_Using_ML_DL.pptx` – presentation built on the notebook outputs.  
- (Data are **not** included here; they must be downloaded separately following MIMIC-III access rules.)

### Citation & Ethics

- **MIMIC-III citation** (recommended):  
  Johnson AE, Pollard TJ, Shen L, et al. *MIMIC-III, a freely accessible critical care database.* Scientific Data 3, 160035 (2016).

- **Usage**:
  - MIMIC-III contains deidentified health data under strict access requirements.  
  - Ensure you have completed required training and follow all data use policies.  
  - Plots and models built from MIMIC-III are for research and educational purposes only and are **not** intended for clinical decision making.

