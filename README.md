# Loan Risk Analysis

A machine learning project that explores loan application data and
compares models for identifying good and bad loan outcomes.

## Project Overview

The goal of this project is to understand the available loan data,
prepare it for analysis, and compare two classification models:

-   Logistic Regression
-   Random Forest

The notebook evaluates the models using accuracy, precision, recall,
F1-score, and ROC-AUC.

## Dataset

The notebook reads two sheets from `Assessment_-_Data_Scientist.xlsx`:

-   **Application Data** --- customer and application details.
-   **Loan Performance** --- loan identifiers and the `flgGood` outcome.

The target is mapped as:

-   `Bad` → `1`
-   `Good` → `0`

> **Dataset note:** Include the original Excel file in this repository
> only if you have permission to share it. If the dataset is
> confidential or belongs to an assessment provider, keep it private and
> update the notebook's file path or instructions as needed.

## Workflow

1.  Load the application and loan performance sheets.
2.  Explore the rows, columns, data types, missing values, and duplicate
    records.
3.  Prepare customer keys and match the two datasets.
4.  Select input features and encode the loan outcome.
5.  Split the data into training and testing sets.
6.  Handle missing values, convert categorical columns into dummy
    variables, and scale numerical features.
7.  Train Logistic Regression and Random Forest models.
8.  Compare the models using evaluation metrics.
9.  Review plots for loan outcome distribution, credit-score patterns,
    feature importance, and ROC curves.

## Results

In the current notebook output, Logistic Regression performed better
than Random Forest on the reported test metrics.

  Metric        Logistic Regression   Random Forest
  ----------- --------------------- ---------------
  Accuracy                    0.646           0.608
  Precision                   0.662           0.643
  Recall                      0.718           0.634
  F1-score                    0.689           0.638
  ROC-AUC                     0.693           0.641

Because `Bad` is encoded as `1`, recall measures the proportion of
actual bad loans identified by the model. Logistic Regression's recall
of approximately 0.718 means it identified about 72% of bad loans in
this test set.

These are preliminary results from the current notebook and should not
be treated as evidence that the model is ready for real lending
decisions. Further validation is needed, including checks for repeated
customers across the train/test split, feature availability at decision
time, and model fairness.

## Project Structure

``` text
loan-risk-analysis/
├── loan_risk_analysis.ipynb
├── Assessment_-_Data_Scientist.xlsx
├── README.md
└── requirements.txt
```

If you do not have permission to publish the Excel dataset, omit it from
the public repository and explain how an authorized user can place the
file locally.

## Installation

Use Python 3.10 or later, then install the required packages:

``` bash
python -m pip install -r requirements.txt
```

## Run the Notebook

1.  Clone or download this repository.

2.  Place `Assessment_-_Data_Scientist.xlsx` in the same folder as the
    notebook, if you are authorized to access the dataset.

3.  Install the requirements.

4.  Start Jupyter:

    ``` bash
    jupyter notebook
    ```

5.  Open `loan_risk_analysis.ipynb` and run the cells from top to
    bottom.

The notebook expects the Excel file to have the exact filename shown
above and to contain the `Application Data` and `Loan Performance`
sheets.

## Tools Used

-   Python
-   Pandas and NumPy
-   Matplotlib and Seaborn
-   Scikit-learn
-   Jupyter Notebook

## Disclaimer

This project is for learning and exploratory analysis. It is not a
validated credit-scoring system and should not be used by itself to
approve or reject real loan applications.
