### AI in Healthcare

This repository is a collection of small, self-contained projects exploring machine learning, deep learning, and data visualization in healthcare. Each project lives in its own subfolder under `ai-in-healthcare` and is intended to be runnable and understandable on its own.

### Repository Layout

- **`ML_DL_tutorial/`**  
  Introductory machine learning and deep learning examples for healthcare, including a notebook (`healthcare_ml_dl.ipynb`) and a presentation on predicting hospital mortality.

- **`mimic_visualization/`**  
  Visual exploration of the MIMIC-III ICU database, focusing on patient demographics, admissions patterns, mortality, length of stay, and ICU medications. Contains a Jupyter notebook and a talk-ready slide deck.

### How to Work with a Subproject

1. **Navigate into the folder**  
   ```bash
   cd ai-in-healthcare/<project-folder>
   ```
2. Read the local `README.md` or notebook header.
   Each project should document:
   - Goal and dataset  
   - Environment / dependencies  
   - How to run (e.g., which notebook or script to execute)
3. **Create and activate an environment (optional but recommended)**  
   Use `conda` or `venv` to isolate dependencies per project if they diverge.

### Data, Privacy, and Ethics

- Many healthcare datasets (e.g., MIMIC-III) require special access and training.  
- Keep raw patient-level data **out of version control** (`.gitignore` them) and store only code, configs, and documentation.  
- All analyses in this repository are for **research and educational purposes only** and are not intended for clinical decision-making.

