# Titanic-EDA# Titanic Dataset - Exploratory Data Analysis (EDA)

## Objective

The objective of this project is to perform Exploratory Data Analysis (EDA) on the Titanic dataset using Python. The analysis aims to identify patterns, relationships, trends, and anomalies through statistical summaries and visualizations.

## Tools Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

## Dataset

Titanic Dataset containing passenger information such as:

* Passenger Class
* Gender
* Age
* Fare
* Embarked Port
* Survival Status

## Steps Performed

### 1. Data Loading

The dataset was loaded using Pandas and inspected using:

* head()
* info()
* describe()

### 2. Data Cleaning

* Missing values in Age were filled using median values.
* Missing values in Embarked were filled using mode.
* Cabin column was dropped due to excessive missing values.

### 3. Statistical Analysis

Performed:

* Summary statistics
* Missing value analysis
* Value counts for categorical variables

### 4. Visualizations

Created:

* Histograms
* Boxplots
* Countplots
* Scatterplots
* Correlation Heatmap
* Pairplot

### 5. Key Insights

#### Survival Analysis

* Female passengers had a significantly higher survival rate than males.
* First-class passengers were more likely to survive.

#### Age Distribution

* Most passengers were between 20 and 40 years old.

#### Fare Analysis

* Fare contained several outliers.
* Higher fare passengers showed better survival probability.

#### Passenger Class

* Majority of passengers belonged to Third Class.
* Third-class passengers had the highest mortality rate.

### Conclusion

The analysis indicates that Gender, Passenger Class, and Fare were the most influential factors affecting passenger survival on the Titanic. Female passengers and First-Class passengers had the highest survival probability.

## Outcome

This project demonstrates the use of Exploratory Data Analysis techniques to discover meaningful insights and patterns from real-world data using Python.
