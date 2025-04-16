# 🧠 Visualizing Lifestyle Patterns Affecting Obesity Using Python

**Project Title:** Obesity Level Analysis Using Data Visualization Techniques  
**Course:** Introduction to Data Science Toolbox (INT375)  
**Semester:** January – April 2025  
**University:** Lovely Professional University  
**Student:** Sachin Ravi (Reg. No: 12306922)  
**Program:** B.Tech (CSE) – K23EV  
**Guided by:** Mrs. Sandeep Kaur (School of CSE/IT)

---

## 📌 Introduction

Obesity is a serious public health concern impacted by various lifestyle and behavioral factors. This project explores patterns in obesity levels through **data visualization** using Python libraries. We perform Exploratory Data Analysis (EDA) to extract insights from a dataset of individuals, using tools like **Seaborn**, **Matplotlib**, and **Pandas**.

---

## 📂 Dataset Overview

- **File:** `ObesityDataSet_raw_and_data_sinthetic.csv`  
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/) or Kaggle  
- **Features Include:**
  - Gender, Age, Education
  - Meals per day, Vegetable consumption (FCVC)
  - Physical Activity Frequency (FAF), Alcohol Consumption (CALC)
  - Mode of Transport (MTRANS)
  - Target: `NObeyesdad` (Obesity Level)

---

## 🧪 EDA Highlights

### 1. 📊 Obesity Level Distribution
- Visualized with a **bar plot** using `countplot`.
- Highlights prevalence of obesity categories.

### 2. 🥗 Physical Activity vs Obesity
- **Pie chart** shows mean FAF per obesity class.
- Higher physical activity → healthier weight.

### 3. 🍽️ Meals Per Day
- Analyzed daily meals (`NCP`) with **barplot**.
- Both over- and under-eating trends impact obesity.

### 4. 🥦 Vegetable Consumption (FCVC)
- **Strip plot** analysis.
- Frequent vegetable consumption → normal/healthy range.

### 5. 🚲 Transportation Mode
- **Grouped bar chart** shows:
  - Sedentary transport → higher obesity.
  - Active transport (bike/walk) → healthier outcomes.

### 6. 🍷 Alcohol Consumption
- **Stacked bar chart** shows correlation with obesity.
- More frequent alcohol consumption links to obesity.

### 7. 🧍 BMI vs Age
- **Scatter plot** (BMI vs Age) colored by health status.
- Unhealthy individuals cluster in 20–30 age range with high BMI.

### 8. 🧬 Correlation Heatmap
- **Heatmap** of numeric columns.
- BMI is strongly correlated with weight, activity, and health markers.

### 9. 🧮 BMI Distribution
- **Histogram + KDE** of BMI by health status.
- Healthy group centered in normal BMI range.

---

## ✅ Conclusion

The study shows how physical activity, dietary habits (meals, veggies), and transportation modes significantly influence obesity. Visual patterns clearly show that healthier lifestyle choices correlate with lower obesity levels.

---

## 🔮 Future Scope

- Add violin plots and box plots for deeper demographic insights
- Integrate machine learning models for predictive classification
- Expand analysis on gender and age interactions
- Include interactive dashboards using Plotly or Streamlit

---

## 📚 References

1. [UCI ML Repository](https://archive.ics.uci.edu/)
2. [Seaborn Docs](https://seaborn.pydata.org/)
3. [Matplotlib Docs](https://matplotlib.org/)
4. [NumPy Docs](https://numpy.org/)

---

> ✨ *This project was completed as part of the INT375 course at LPU, under the guidance of Mrs. Sandeep Kaur Ma’am.*
>
> import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Load the dataset
df = pd.read_csv(r"C:\Users\mahas\OneDrive\maha1\Documents\BOOKS\ObesityDataSet_raw_and_data_sinthetic.csv")

# Set Seaborn style
sns.set(style="whitegrid")

# ------------------------------------------------
# 1. Distribution of Obesity Levels (Bar Plot)
# ------------------------------------------------
plt.figure(figsize=(10, 6))
sns.countplot(data=df, x='NObeyesdad', order=df['NObeyesdad'].value_counts().index, palette='coolwarm')
plt.title('1. Distribution of Obesity Levels')
plt.xlabel('Obesity Category')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 2. Average Physical Activity (FAF) by Obesity Level (Pie Chart)
# ------------------------------------------------
avg_faf = df.groupby('NObeyesdad')['FAF'].mean().sort_values(ascending=False)
plt.figure(figsize=(8, 8))
plt.pie(avg_faf, labels=avg_faf.index, autopct='%1.1f%%', startangle=140, colors=sns.color_palette('viridis', len(avg_faf)))
plt.title('2. Average Physical Activity (FAF) by Obesity Level')
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 3. Average Number of Meals (NCP) by Obesity Level (Bar Plot)
# ------------------------------------------------
plt.figure(figsize=(10, 6))
sns.barplot(data=df, x='NObeyesdad', y='NCP', estimator=np.mean, errorbar=None, hue='NObeyesdad', palette='magma', legend=False)
plt.title('3. Average Number of Meals (NCP) by Obesity Level')
plt.xlabel('Obesity Category')
plt.ylabel('Avg. Meals per Day')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 4. Vegetable Consumption (FCVC) vs Obesity (Strip Plot)
# ------------------------------------------------
plt.figure(figsize=(10, 6))
sns.stripplot(data=df, x='NObeyesdad', y='FCVC', hue='NObeyesdad', dodge=True, jitter=True, palette='cubehelix', size=3, legend=False)
plt.title('4. Vegetable Consumption (FCVC) vs Obesity - Strip Plot')
plt.xlabel('Obesity Category')
plt.ylabel('Frequency of Vegetable Consumption')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 5. Mode of Transportation vs Obesity Level (Grouped Bar Chart)
# ------------------------------------------------
plt.figure(figsize=(10, 6))
sns.countplot(data=df, x='MTRANS', hue='NObeyesdad', palette='Set2')
plt.title('5. Mode of Transportation and Obesity Levels')
plt.xlabel('Mode of Transportation')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 6. Alcohol Consumption and Obesity (Stacked Bar Chart)
# ------------------------------------------------
alcohol_data = pd.crosstab(df['CALC'], df['NObeyesdad'])
alcohol_data.plot(kind='bar', stacked=True, colormap='cool', figsize=(10, 6))
plt.title('6. Alcohol Consumption and Obesity Levels (Stacked Bar Chart)')
plt.xlabel('Alcohol Consumption Frequency')
plt.ylabel('Count')
plt.xticks(rotation=0)
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 7. Health Status Classification and BMI Calculations
# ------------------------------------------------
df['BMI'] = df['Weight'] / (df['Height'] ** 2)

# Define Health Status
healthy = ['Normal_Weight']
unhealthy = ['Overweight_Level_I', 'Overweight_Level_II', 'Obesity_Type_I', 'Obesity_Type_II', 'Obesity_Type_III']
df['Health_Status'] = df['NObeyesdad'].apply(lambda x: 'Healthy' if x in healthy else 'Unhealthy')

# ------------------------------------------------
# 8. Violin Plot: Age by Gender and Health Status
# ------------------------------------------------
plt.figure(figsize=(10, 6))
sns.violinplot(data=df, x='Gender', y='Age', hue='Health_Status', split=True)
plt.title('Age Distribution by Gender and Health Status (Violin Plot)')
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 9. Box Plot: BMI by Gender and Health Status
# ------------------------------------------------
plt.figure(figsize=(10, 6))
sns.boxplot(data=df, x='Gender', y='BMI', hue='Health_Status')
plt.title('BMI by Gender and Health Status (Box Plot)')
plt.tight_layout()
plt.show()

# ------------------------------------------------
# 10. Grouped Bar Plot: Gender vs Health Status
# ------------------------------------------------
plt.figure(figsize=(8, 6))
sns.countplot(data=df, x='Gender', hue='Health_Status')
plt.title('Count of Health Status by Gender (Grouped Bar Plot)')
plt.tight_layout()
plt.show()

