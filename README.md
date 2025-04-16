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
