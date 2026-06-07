# 🚢 Titanic Dataset - Exploratory Data Analysis (EDA)

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on the famous Titanic Dataset using Python. The objective is to analyze passenger information and identify patterns, relationships, trends, and factors that influenced passenger survival during the Titanic disaster.

EDA helps transform raw data into meaningful insights through statistical summaries and visualizations.

---

## 🎯 Objective

The main objectives of this project are:

* Understand the structure of the Titanic dataset.
* Identify missing values and data quality issues.
* Perform data cleaning and preprocessing.
* Analyze statistical properties of the dataset.
* Visualize patterns and relationships.
* Discover factors affecting passenger survival.
* Generate meaningful insights from data.

---

## 🛠️ Tools & Libraries Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 📂 Dataset Information

Dataset: Titanic Dataset

Features included:

| Feature     | Description             |
| ----------- | ----------------------- |
| PassengerId | Passenger ID            |
| Survived    | Survival Status         |
| Pclass      | Passenger Class         |
| Name        | Passenger Name          |
| Sex         | Gender                  |
| Age         | Age                     |
| SibSp       | Siblings/Spouses aboard |
| Parch       | Parents/Children aboard |
| Ticket      | Ticket Number           |
| Fare        | Ticket Fare             |
| Cabin       | Cabin Number            |
| Embarked    | Port of Embarkation     |

Dataset Shape:

```python
df.shape
```

Output:

```python
(891, 12)
```

---

## 📊 Exploratory Data Analysis Steps

### 1. Import Required Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

### 2. Load Dataset

```python
df = pd.read_csv('train.csv')
df.head()
```

---

### 3. Dataset Information

```python
df.info()
```

Purpose:

* Check data types
* Check missing values
* Understand dataset structure

---

### 4. Statistical Summary

```python
df.describe()
```

Purpose:

* Mean
* Median
* Standard Deviation
* Minimum and Maximum Values

---

### 5. Missing Value Analysis

```python
df.isnull().sum()
```

Output revealed missing values in:

* Age
* Cabin
* Embarked

---

### 6. Data Cleaning

```python
df['Age'].fillna(df['Age'].median(), inplace=True)

df['Embarked'].fillna(
    df['Embarked'].mode()[0],
    inplace=True
)

df.drop('Cabin', axis=1, inplace=True)
```

---

## 📈 Visualizations Performed

### Age Distribution Histogram

```python
plt.hist(df['Age'], bins=20)
plt.title('Age Distribution')
plt.show()
```

Observation:

* Most passengers were between 20 and 40 years old.

---

### Fare Distribution Boxplot

```python
sns.boxplot(x=df['Fare'])
plt.show()
```

Observation:

* Significant outliers exist in fare values.

---

### Survival Count Plot

```python
sns.countplot(x='Survived', data=df)
plt.show()
```

Observation:

* More passengers died than survived.

---

### Survival by Gender

```python
sns.countplot(
    x='Sex',
    hue='Survived',
    data=df
)
plt.show()
```

Observation:

* Females had a higher survival rate.

---

### Survival by Passenger Class

```python
sns.countplot(
    x='Pclass',
    hue='Survived',
    data=df
)
plt.show()
```

Observation:

* First-Class passengers survived more frequently.

---

### Scatter Plot

```python
sns.scatterplot(
    x='Age',
    y='Fare',
    hue='Survived',
    data=df
)
plt.show()
```

Observation:

* Higher fare passengers generally had better survival chances.

---

### Correlation Heatmap

```python
numeric_df = df.select_dtypes(
    include=['number']
)

sns.heatmap(
    numeric_df.corr(),
    annot=True,
    cmap='coolwarm'
)

plt.show()
```

Observation:

* Fare positively correlates with survival.
* Passenger Class negatively correlates with survival.

---

### Pairplot

```python
sns.pairplot(
    df[['Survived',
        'Age',
        'Fare',
        'Pclass']],
    hue='Survived'
)

plt.show()
```

Observation:

* Fare and Passenger Class are important indicators of survival.

---

## 🔍 Key Findings

### 1. Gender Impact

Female passengers had significantly higher survival rates than male passengers.

### 2. Passenger Class Impact

First-Class passengers had the highest probability of survival.

### 3. Fare Influence

Passengers paying higher fares generally showed better survival rates.

### 4. Age Distribution

Most passengers were between 20 and 40 years old.

### 5. Missing Data

The dataset contained missing values that required preprocessing.

### 6. Outliers

Fare distribution contained multiple extreme outliers.

---

## 📋 Results Summary

* Dataset contains 891 passenger records.
* Missing values were handled successfully.
* Cabin column was removed due to excessive missing data.
* Female passengers survived more frequently.
* First-Class passengers had better survival chances.
* Fare and Passenger Class strongly influenced survival.
* Age showed weaker correlation with survival.

---

## 📁 Project Structure

```text
Titanic-EDA/
│
├── Titanic_EDA.ipynb
├── Titanic_EDA_Report.pdf
├── train.csv
├── screenshots/
│   ├── histogram.png
│   ├── boxplot.png
│   ├── survival_gender.png
│   ├── heatmap.png
│   └── pairplot.png
│
└── README.md
```

---

## 🎓 Learning Outcomes

Through this project, the following skills were developed:

* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* Data Visualization
* Correlation Analysis
* Statistical Interpretation
* Insight Generation
* Python Programming

---

## ✅ Conclusion

The Titanic Dataset EDA successfully identified important patterns affecting passenger survival. Gender, Passenger Class, and Fare emerged as the strongest factors influencing survival outcomes. This project demonstrates how Exploratory Data Analysis can be used to understand datasets, identify trends, detect anomalies, and generate meaningful insights before building predictive models.
