# ECG Heartbeat Classification

This project is a CS280 / CS485 Introduction to AI lab notebook for supervised ECG heartbeat classification.

The notebook compares four classical machine learning models on the MIT-BIH heartbeat dataset and selects a final model using validation performance. The official test set is kept for final evaluation only.

## Project Files

```text
Lab_project/
|- ECG_Heartbeat_Classification.ipynb
|- README.md
|- requirements.txt
`- data/
   |- mitbih_train.csv
   `- mitbih_test.csv
```

## Notebook Workflow

The notebook is organized for classroom presentation:

1. Problem definition
2. Dataset loading and schema validation
3. Class distribution and example ECG waveform visualization
4. Train / validation / official test split
5. Metrics from class: accuracy, precision, recall, and F1-score
6. Model definitions
7. Hyperparameter tuning with cross-validation
8. Validation comparison and model selection
9. Official test evaluation
10. Normal-vs-abnormal interpretation
11. Inference on one unseen ECG heartbeat

## Models Compared

- Logistic Regression
- K-Nearest Neighbors
- Random Forest
- Support Vector Machine

## Main Evaluation Metrics

The notebook uses confusion-matrix metrics studied in class:

```text
Accuracy = (TP + TN) / (TP + TN + FP + FN)
Precision = TP / (TP + FP)
Recall = TP / (TP + FN)
F1 = 2 * Precision * Recall / (Precision + Recall)
```

Because the dataset is strongly imbalanced, model selection prioritizes:

- Macro F1
- Macro Recall
- Abnormal Macro Recall
- Accuracy as a secondary metric

## Reproducible Setup

Recommended Python version:

- `Python 3.12.10`

Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

Register the notebook kernel:

```powershell
python -m ipykernel install --user --name ecg-lab-project --display-name "Python (ECG Lab Project)"
```

## Running the Notebook

Open:

- `ECG_Heartbeat_Classification.ipynb`

Then:

1. Select the kernel `Python (ECG Lab Project)`.
2. Make sure the `data/` folder is next to the notebook.
3. Run the notebook from top to bottom.
4. Before presentation or submission, restart the kernel, run all cells, and save the notebook with visible outputs.

## Notes

- The notebook expects the CSV files inside the local `data/` folder.
- The final selected model in the current executed notebook is Random Forest.
- If package imports fail, verify that the selected Jupyter kernel uses the `.venv` environment where `requirements.txt` was installed.
