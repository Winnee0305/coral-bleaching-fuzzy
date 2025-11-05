### Coral Bleaching Fuzzy Inference Project

This repository contains a small workflow for exploring coral bleaching data and building a fuzzy logic model to infer bleaching risk from environmental variables. It includes data cleaning, visualization, and a fuzzy inference system implemented in Jupyter notebooks.

## Project Structure

- `dataset_cleaning.ipynb`: Data loading and cleaning pipeline for raw datasets.
- `dataset_visualisation.ipynb`: Exploratory analysis and visualizations of cleaned data.
- `fuzzy_logic.ipynb`: Fuzzy sets, rules, and inference system to estimate bleaching risk.
- `global_bleaching_environmental.csv`: Raw dataset (global environmental factors).
- `cleaned_data.csv`: Cleaned dataset produced by the cleaning notebook.
- `sample.csv`: Small sample for quick experimentation/testing.
- `README.md`: This file.

## Requirements

- Python 3.9+ (3.11+ recommended)
- Jupyter Notebook or JupyterLab
- Recommended packages:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
  - `scikit-fuzzy` (a.k.a. `skfuzzy`)

Install dependencies (use a virtual environment if possible):

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
pip install --upgrade pip
pip install numpy pandas matplotlib seaborn scikit-fuzzy jupyter
```

## Quick Start

1. Activate your environment and launch Jupyter:
   ```bash
   source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
   jupyter notebook
   ```
2. Open and run notebooks in this order:
   - `dataset_cleaning.ipynb`
   - `dataset_visualisation.ipynb`
   - `fuzzy_logic.ipynb`

If you want a quick run without the full dataset, try `sample.csv` where applicable.

## Data Notes

- The fuzzy model expects environmental variables commonly linked to bleaching (e.g., sea surface temperature anomalies, degree heating weeks, etc.).
- `global_bleaching_environmental.csv` is the raw source. After running `dataset_cleaning.ipynb`, `cleaned_data.csv` is generated and used in the later steps.

## Fuzzy Logic Overview

- Define linguistic variables (e.g., Temperature: low/medium/high; Heat Stress: mild/moderate/severe).
- Construct membership functions for each variable using `scikit-fuzzy`.
- Specify a rule base that maps environmental conditions to bleaching risk.
- Apply fuzzy inference and defuzzify to obtain a crisp bleaching risk score.

You can tweak term boundaries, membership shapes, and rules in `fuzzy_logic.ipynb` to test sensitivity and improve alignment with domain knowledge.

## Results and Outputs

- Plots from `dataset_visualisation.ipynb` summarize distributions and relationships.
- `fuzzy_logic.ipynb` outputs membership function plots and inferred bleaching risk scores.
