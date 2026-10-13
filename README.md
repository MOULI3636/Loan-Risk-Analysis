
# Loan Risk Analysis

A machine learning project that analyzes loan application data and compares models for identifying good and bad loan outcomes.

## Project Overview

The goal of this project is to explore loan data, prepare it for analysis, and compare two classification models:

- Logistic Regression
- Random Forest

The models are evaluated using accuracy, precision, recall, F1-score, and ROC-AUC.

## Dataset

The notebook reads two sheets from `Assessment_-_Data_Scientist.xlsx`:

- **Application Data** — customer and application details.
- **Loan Performance** — loan identifiers and the `flgGood` outcome.

The target variable is mapped as follows:

- `Bad` → `1`
- `Good` → `0`

> **Dataset note:** Include the original Excel file in this repository only if you have permission to share it. If the dataset is confidential or belongs to an assessment provider, do not publish it publicly. Update the notebook's file path and instructions accordingly.

## Workflow

1. Load the application and loan performance sheets.
2. Explore the data, including column types, missing values, and duplicate records.
3. Prepare customer keys and match the two datasets.
4. Select input features and encode the target variable.
5. Split the data into training and testing sets.
6. Handle missing values, encode categorical features, and scale numerical features.
7. Train Logistic Regression and Random Forest models.
8. Evaluate and compare model performance.
9. Review plots showing loan outcomes, credit-score patterns, feature importance, and ROC curves.

## Results

Logistic Regression performed better than Random Forest across all five evaluation metrics in the current test results.

| Metric | Logistic Regression | Random Forest |
|:---|---:|---:|
| Accuracy | 0.646 | 0.608 |
| Precision | 0.662 | 0.643 |
| Recall | 0.718 | 0.634 |
| F1-score | 0.689 | 0.638 |
| ROC-AUC | 0.693 | 0.641 |

Since `Bad` is encoded as `1`, recall measures the proportion of actual bad loans correctly identified by the model. Logistic Regression achieved a recall of approximately 71.8%, identifying around 72% of bad loans in the test set.

These results provide an initial assessment of the models' performance. Further validation is necessary, including checks for customer overlap between training and testing data, feature availability at the time of a lending decision, and potential model bias, before considering any real-world application.

## Project Structure

```text
loan-risk-analysis/
├── loan_risk_analysis.ipynb
├── Assessment_-_Data_Scientist.xlsx
├── README.md
└── requirements.txt
```

If you do not have permission to publish the Excel dataset, exclude it from the public repository and provide instructions for obtaining and placing the authorized dataset locally.

## Installation

Use Python 3.10 or later and install the required packages:

```bash
python -m pip install -r requirements.txt
```

## Run the Notebook

1. Clone or download the repository.
2. Place `Assessment_-_Data_Scientist.xlsx` in the same folder as the notebook, if you are authorized to access the dataset.
3. Install the required packages.
4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `loan_risk_analysis.ipynb` and run the cells from beginning to end.

The notebook expects the Excel file to have the exact filename shown above and to contain the `Application Data` and `Loan Performance` sheets.

## Tools Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook

## Disclaimer

This project is intended for educational and exploratory purposes. The models have not been validated for operational credit-risk assessment and should not be used as the sole basis for lending decisions. Any real-world use would require further performance validation, fairness assessment, appropriate data governance, and review of applicable regulatory requirements.
