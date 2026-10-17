# Loan Approval Classification

A machine-learning web application built with **Streamlit** that
predicts whether a loan application is likely to be approved or rejected
based on applicant and loan details.

> **Disclaimer:** This project is for educational and demonstration
> purposes only. Its predictions are not financial advice and should not
> be used as the sole basis for real lending decisions.

## Features

-   Interactive interface for entering applicant and loan information.
-   Loads a saved machine-learning pipeline for predictions.
-   Displays **Loan Approved** or **Loan Rejected**.
-   Includes an exploratory data analysis (EDA) notebook and supporting
    datasets.

## Dataset

This project uses the [Loan Approval Classification dataset on
Kaggle](https://www.kaggle.com/datasets/taweilo/loan-approval-classification-data).

The dataset description reports 45,000 records and 14 variables. The
target is `loan_status` (`1` = approved, `0` = rejected).

### Input features

  -----------------------------------------------------------------------
  Feature                             Description
  ----------------------------------- -----------------------------------
  `person_age`                        Applicant's age

  `person_gender`                     Applicant's gender

  `person_education`                  Highest education level

  `person_income`                     Annual income

  `person_emp_exp`                    Years of employment experience

  `person_home_ownership`             Home ownership status

  `loan_amnt`                         Requested loan amount

  `loan_intent`                       Purpose of the loan

  `loan_int_rate`                     Loan interest rate

  `loan_percent_income`               Loan amount as a proportion of
                                      annual income

  `cb_person_cred_hist_length`        Length of credit history in years

  `credit_score`                      Applicant's credit score

  `previous_loan_defaults_on_file`    Indicator of previous loan defaults
  -----------------------------------------------------------------------

## Project structure

The application expects files to be arranged approximately like this:

``` text
Loan Approval/
├── app.py
├── README.md
├── requirement.txt
├── assets/
│   └── AI Loan Approval Icon.png
├── best_model/
│   └── best_model_pipeline.pkl
└── datasets/
│   ├── cleaned_data.csv
│   ├── loan_data.csv
│   └── model_performance_data.csv
├── myenv/
├── notebooks/
    └── EDA.ipynb
```

The paths must match those in `app.py`. The app loads
`best_model/best_model_pipeline.pkl` and `datasets/cleaned_data.csv`.

## Requirements

-   Python and pip
-   Packages listed in `requirement.txt`: NumPy, pandas, Matplotlib,
    Seaborn, Streamlit, and scikit-learn

## Installation (Windows PowerShell)

Run these commands from the project root folder.

### 1. Create a virtual environment

``` powershell
python -m venv myenv
```

### 2. Activate it

``` powershell
.\myenv\Scripts\Activate.ps1
```

If PowerShell blocks activation, run:

``` powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned
.\myenv\Scripts\Activate.ps1
```

### 3. Install dependencies

``` powershell
python -m pip install --upgrade pip
python -m pip install -r requirement.txt
```

### 4. Run the app

``` powershell
python -m streamlit run app.py
```

Open the local URL printed in the terminal (usually
`http://localhost:8501`).

## How to use

1.  Start the application.
2.  Enter applicant and loan details.
3.  Click **Predict Loan**.
4.  Review the prediction shown on screen.

## Model and analysis

`EDA.ipynb` contains exploratory data analysis and model development.
The notebook uses preprocessing with `OneHotEncoder` for categorical
features and `StandardScaler` for numerical features, followed by
classification models. The selected pipeline is saved as
`best_model_pipeline.pkl` and loaded by the Streamlit app.

The model name and performance metrics should be verified by rerunning
the notebook; this README does not claim a specific accuracy score.

## Troubleshooting

-   **Streamlit launcher references an old Python path:** activate the
    environment and use `python -m streamlit run app.py`.
-   **Model or dataset not found:** check the folder names and paths
    shown in the project structure.
-   **Missing packages:** activate the environment and run
    `python -m pip install -r requirement.txt`.
-   **Icon not found:** ensure `assets/AI Loan Approval Icon.png` exists
    or update the image path in `app.py`.

## Limitations

-   The dataset is synthetic and may not represent real-world
    applicants.
-   Dataset documentation warns that some ages may exceed 100; inspect
    these records during data cleaning.
-   Predictions depend on training data, preprocessing, model quality,
    and user inputs.
-   A production lending system would require careful validation,
    fairness and bias assessment, privacy safeguards, explainability,
    and human oversight.

## Acknowledgements

-   Dataset: [Loan Approval Classification Data ---
    Kaggle](https://www.kaggle.com/datasets/taweilo/loan-approval-classification-data)
-   Technologies: Python, pandas, scikit-learn, and Streamlit
