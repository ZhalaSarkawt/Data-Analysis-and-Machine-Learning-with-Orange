# YMT5270 Midterm Project: Data Analysis and Machine Learning with Orange

## Student Information

* **Full Name**: Zhala Sarkawt Othman
* **Email**: *(zhala.sarkawt@gmail.com)*

## Project Summary

> This project analyzes the "Mental Health in Tech Survey" dataset, sourced from Kaggle, to explore patterns in mental health treatment among tech workers. The goal is to predict whether an individual has sought mental health treatment based on demographic and workplace factors. Orange Data Mining was used for Exploratory Data Analysis (EDA), preprocessing, and machine learning classification without requiring any programming. Key preprocessing steps included imputation for missing values and removal of outliers. Two classification models were tested: Logistic Regression and Random Forest. Random Forest achieved the best performance with an accuracy of 72.2% and an AUC of 0.788. Family history, work interference, and benefits were the most important features influencing treatment prediction. This project demonstrates the effectiveness of visual data mining tools like Orange in building interpretable ML workflows.

### 🔶 Orange Workflow
![Orange Workflow](img/orange_workflow.png)


## Dataset

### Dataset Information

* **Dataset Name**: Mental Health in Tech Survey
* **Source**: [Kaggle - OSMI Mental Health in Tech Survey](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey)
* **License**: Open (for educational/public use)
* **Dataset Size**: 1,259 rows, 26 columns

### Dataset Description

> The dataset includes responses from individuals working in tech-related roles, collected by the Open Sourcing Mental Illness (OSMI) initiative. It covers a variety of factors, such as age, gender, family mental health history, workplace support, and whether the respondent has sought treatment. Some values are missing or inconsistent (especially in age and gender), which required cleaning. The target variable for classification is `treatment`, indicating whether the person has sought mental health treatment.

### Feature Descriptions

| Feature Name    | Data Type   | Description                                     | Example      |
| --------------- | ----------- | ----------------------------------------------- | ------------ |
| Age             | Numerical   | Age of respondent                               | 29           |
| Gender          | Categorical | Self-reported gender                            | "Male"       |
| family\_history | Categorical | Family history of mental illness                | "Yes"        |
| work\_interfere | Categorical | Impact of mental health on work                 | "Often"      |
| remote\_work    | Categorical | Whether respondent works remotely               | "Yes"        |
| benefits        | Categorical | Availability of mental health benefits          | "Don't know" |
| care\_options   | Categorical | Access to mental health care options at work    | "No"         |
| tech\_company   | Categorical | Whether the employer is a tech company          | "Yes"        |
| treatment       | Categorical | Target: whether respondent has sought treatment | "Yes"        |

## Exploratory Data Analysis (EDA)

### Basic Statistics

> * Age: Mean = 32.1, Min = 18, Max = 72 (outliers > 100 removed)
> * Gender: normalized to standard categories (e.g., Male, Female, Non-binary)
> * 2.4% missing data across features; handled via imputation

### Data Preprocessing

* Imputed missing values in `age`, `gender`, and `work_interfere`
* Removed extreme outliers in age (> 100 or < 18)
* Encoded categorical variables (One-Hot or Label Encoding)
* Ignored irrelevant columns: `Timestamp`, `state`, `country`

### Visualizations

#### Visualization 1: Target vs Treatment Column
![Target Treatment Column](img/target_treatment.png)
> This visualization shows the distribution of the `treatment` target variable.

> Shows a moderate class imbalance between those who sought treatment vs. those who did not.

#### Visualization 2: Family History vs Treatment



> Strong correlation between family mental illness history and likelihood of seeking treatment.

### Feature Relationships

> Feature correlation matrix and scatter plots revealed that `family_history`, `work_interfere`, and `benefits` were most predictive. Age and gender showed some correlation but were less significant.

## Machine Learning Application

### Method Used

> Classification was chosen to predict a binary target variable (`treatment`). This method suits the goal of determining whether individuals are likely to seek treatment based on workplace and personal factors.

### Models and Parameters

* **Logistic Regression**: Default settings
* **Random Forest**: Trees = 10, Random State = 42

(Include Orange widget screenshots here if required)

### Model Evaluation

| Metric    | Logistic Regression | Random Forest |
| --------- | ------------------- | ------------- |
| Accuracy  | 65.9%               | 72.2%         |
| AUC       | 0.747               | 0.788         |
| F1 Score  | 0.646               | 0.722         |
| Precision | 0.684               | 0.722         |
| Recall    | 0.659               | 0.722         |
| MCC       | 0.340               | 0.444         |

### Model Değerlendirmesi

### Model Evaluation

#### Test & Score Widget Output
![Test Score](img/test_score.png)
> This figure shows the comparative metrics of the applied models.

#### Confusion Matrix
![Confusion Matrix](img/confusion_matrix.png)
> This matrix displays the distribution of predicted vs actual class labels.


### Interpretation of Results

> Random Forest outperformed Logistic Regression across all metrics. This model effectively captured non-linear patterns in the data. Important features were work-related, rather than demographic. Limitations included inconsistent data entries and class imbalance.

## Orange Workflow

> Below is the Orange workflow used in this project. It includes steps for file import, preprocessing, visualization, model training, and evaluation.


## Conclusion and Recommendations

> The project demonstrated the power of visual machine learning tools for classification tasks. Random Forest is recommended for future use due to its strong performance. Future improvements could include additional preprocessing, feature engineering, and trying other ensemble models.

## References

1. [Kaggle Dataset](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey)
2. Orange Data Mining: [https://orangedatamining.com/](https://orangedatamining.com/)

## Appendices

### Orange Project File

> [mental\_health\_project.ows](project/mental_health_project.ows)


