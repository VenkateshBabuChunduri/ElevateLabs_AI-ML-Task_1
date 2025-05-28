# ElevateLabs_AI-ML-Task_1
Data Cleaning &amp; Preprocessing
# AI/ML Internship - Task 1: Data Cleaning & Preprocessing (Titanic Dataset)

## Objective
The primary goal of this task was to apply fundamental data cleaning and preprocessing techniques to a raw dataset. This process is crucial to prepare data for effective machine learning model training.

## Dataset
The dataset used for this task is the renowned [Titanic Dataset](https://www.kaggle.com/c/titanic/data), which provides details about passengers aboard the Titanic.

## Tools and Libraries Used
* **Python**
* **Pandas:** For data manipulation and analysis.
* **NumPy:** For numerical operations.
* **Matplotlib:** For creating static visualizations.
* **Seaborn:** For making statistical graphics, built on Matplotlib.
* **Scikit-learn:** For data preprocessing tools like StandardScaler.

## Data Preprocessing Steps Performed:

### 1. Initial Data Exploration
* Loaded the `Titanic-Dataset.csv` into a Pandas DataFrame.
* Examined the DataFrame's structure, data types, and identified columns with missing values using `df.info()` and `df.isnull().sum()`.
* **Observation:** The dataset contained 891 entries and 12 columns. Missing values were noted in 'Age' (177), 'Cabin' (687), and 'Embarked' (2).

### 2. Handling Missing Values
* **'Age' Column:** Missing values were imputed (filled) with the *median* age to handle potential skewness in the data distribution.
* **'Embarked' Column:** Missing values were filled with the *mode* (most frequent port of embarkation) as it's a categorical feature with few missing entries.
* **'Cabin' Column:** This column was *dropped* entirely due to a very high percentage of missing values (over 75%), which would make meaningful imputation challenging.
* **Observation:** All missing values were successfully addressed, resulting in a dataset with no null entries in the remaining columns.

### 3. Encoding Categorical Features
* **'Name' and 'Ticket' Columns:** These columns were *dropped* as they are generally not useful as direct features for machine learning models without complex feature engineering.
* **'Sex' and 'Embarked' Columns:** These categorical columns were converted into numerical representations using *one-hot encoding*. This created new binary (0 or 1) columns (e.g., 'Sex_male', 'Embarked_Q', 'Embarked_S').
* **Observation:** The dataset was transformed to contain exclusively numerical features, suitable for machine learning algorithms.

### 4. Normalizing Numerical Features
* **Selected Features:** Numerical columns including 'Pclass', 'Age', 'SibSp', 'Parch', and 'Fare' were chosen for normalization.
* **Method:** The `StandardScaler` from Scikit-learn was applied. This method transforms data such that it has a mean of 0 and a standard deviation of 1.
* **Observation:** Numerical features were successfully scaled, ensuring they are on a comparable range, which improves the performance of many machine learning models.

### 5. Outlier Visualization and Removal
* **Visualization:** Box plots were generated for the numerical features to visually inspect for outliers (data points significantly different from the rest).
* **Removal Method:** Outliers were identified and removed using the *Interquartile Range (IQR) method* (values outside 1.5 times the IQR from Q1 or Q3).
* **Observation:** The process effectively identified and removed outliers, reducing the dataset size from **891 entries to 561 entries**. This step helps create a cleaner and more robust dataset.

## Files in this Repository:
* `titanic_data_cleaning.ipynb`: The Python script containing all the data cleaning and preprocessing code.
* `Titanic-Dataset.csv`: The original raw dataset used for this task.
* `numerical_features_boxplots.png`: An image file displaying the box plots of numerical features, visualizing outliers.

---
