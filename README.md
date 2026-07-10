
---

## 🎨 **Bonus: Add a Nice Banner Image (Optional)**

Add this HTML at the top of your README (replace with your own image):

```html
<p align="center">
  <img src="https://img.shields.io/badge/Steel%20Plant-Energy%20Analysis-blue?style=for-the-badge&logo=industry" alt="Steel Plant Energy Analysis">
</p>


# AI-ML-Intern-Task-Week2
# 🏭 Steel Plant Energy Consumption Analysis

### Machine Learning Project for Energy Prediction in Steel Manufacturing

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-blue.svg)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.3%2B-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📊 **Project Overview**

This project performs a comprehensive analysis of energy consumption patterns in a steel manufacturing plant. Using real-world data from a steel industry facility, I built and evaluated multiple machine learning models to predict energy usage and identify key drivers of consumption.

The project follows the complete machine learning workflow:
- **Exploratory Data Analysis** (EDA) with feature engineering
- **Baseline Modeling** with 4 regression algorithms
- **Model Evaluation** and selection

---

## 🎯 **Objectives**

1. **Analyze** energy consumption patterns in steel manufacturing
2. **Engineer** meaningful features from raw data
3. **Build** multiple regression models for energy prediction
4. **Compare** model performance and select the best
5. **Provide** actionable insights for operational optimization

---

## 📁 **Repository Structure**
AI-ML-Intern-Task-Week2/
│
├── steel_plant_energy_analysis.ipynb # Complete analysis (EDA + Modeling)
│
├── data/
│ └── steel_industry_energy.csv # UCI Steel Industry Dataset
│
├── README.md # Project documentation
└── requirements.txt # Python dependencies

---

## 🔍 **Dataset Details**

**Source:** [UCI Machine Learning Repository - Steel Industry Energy Consumption](https://archive.ics.uci.edu/static/public/851/steel+industry+energy+consumption.zip)

**Features:**
- **11 original columns** including:
  - `Usage_kWh`: Target variable (energy consumption in kilowatt-hours)
  - `Load_Type`: Light, Medium, or Maximum load categories
  - `WeekStatus`: Weekend/Weekday classification
  - Power factor and reactive power measurements
  - CO₂ emissions data

- **6 engineered features** added:
  - `hour`: Hour of day (0-23)
  - `day_of_week`: Name of the day
  - `month`: Month number (1-12)
  - `is_weekend`: Binary indicator
  - `Power_Factor_Ratio`: Leading/Lagging power factor ratio
  - `High_Load`: Binary indicator for consumption above 75th percentile

**Statistics:**
- **35,040** records
- **17** total features
- **No missing values** (1 handled via imputation)
- **328 outliers** (0.94% of data)

---

## 🛠️ **Technologies Used**

| Category | Technologies |
|----------|-------------|
| **Language** | Python 3.8+ |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-learn |
| **Development** | Jupyter Notebook |
| **Version Control** | Git, GitHub |

---

## 📊 **Key Findings**

### **Exploratory Data Analysis**

| Finding | Detail |
|---------|--------|
| **Peak Consumption** | 1:00 PM (37.36 kWh average) |
| **Lowest Consumption** | 4:00 AM (15.73 kWh average) |
| **Highest Load Type** | Maximum Load (59.27 kWh average) |
| **Lightest Load Type** | Light Load (8.63 kWh average) |
| **Weekday vs Weekend** | Weekdays show higher consumption |
| **Outliers** | 328 records (0.94%) above 123.29 kWh |

### **Correlation Analysis**

| Feature | Correlation with Usage_kWh |
|---------|---------------------------|
| CO2(tCO2) | 0.988 |
| Lagging_Current_Reactive.Power_kVarh | 0.896 |
| High_Load | 0.868 |
| Lagging_Current_Power_Factor | 0.386 |
| is_weekend | -0.295 |

---

## 🤖 **Model Performance**

After training 4 regression models, here are the results:

| Model | Test RMSE (kWh) | CV RMSE (kWh) | R² Score | MAE (kWh) |
|-------|-----------------|---------------|----------|-----------|
| **Random Forest** | **1.8888** | 2.8966 (±2.0336) | **0.9969** | **0.9160** |
| Decision Tree | 2.3303 | 3.3495 (±1.9393) | 0.9952 | 1.1925 |
| Linear Regression | 4.1460 | 4.6048 (±1.3915) | 0.9849 | 2.6339 |
| Ridge Regression | 6.2666 | 6.6866 (±1.0957) | 0.9655 | 4.3604 |

### **🏆 Best Model: Random Forest Regressor**

**Performance Metrics:**
- **Test RMSE:** 1.8888 kWh
- **Cross-Validation RMSE:** 2.8966 kWh (±2.0336)
- **R² Score:** 0.9969 (explains 99.69% of variance)
- **MAE:** 0.9160 kWh (average error < 1 kWh)

**Feature Importance (Top 5):**
| Feature | Importance |
|---------|------------|
| CO2(tCO2) | **97.85%** |
| Lagging_Current_Reactive.Power_kVarh | 1.46% |
| Lagging_Current_Power_Factor | 0.24% |
| Power_Factor_Ratio | 0.19% |
| Leading_Current_Power_Factor | 0.10% |

---

## 💡 **Key Insights**

### **1. Energy Consumption is Highly Predictable**
- R² of 0.9969 means energy usage can be predicted with near-perfect accuracy
- Enables reliable forecasting for operational planning

### **2. CO₂ Emissions is the Primary Driver**
- Accounts for 97.85% of the predictive power
- Directly proportional to energy consumption in steel production

### **3. Non-Linear Patterns Dominate**
- Tree-based models (Random Forest, Decision Tree) significantly outperform linear models
- Energy consumption patterns are complex and non-linear

### **4. Daily Patterns are Distinct**
- Clear diurnal cycle: peaks during working hours, drops at night
- Consistent weekday vs weekend differences

---

## 🚀 **Getting Started**

### **Installation**

1. **Clone the repository:**
```bash
git clone https://github.com/YOUR-USERNAME/AI-ML-Intern-Task-Week2.git
cd AI-ML-Intern-Task-Week2
Create a virtual environment (recommended):
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pandas==2.0.3
numpy==1.24.3
matplotlib==3.7.1
seaborn==0.12.2
scikit-learn==1.3.0
scipy==1.10.1
jupyter==1.0.0
📈 Visualizations
The notebook includes several key visualizations:

Outlier Detection - Boxplot and distribution of Usage_kWh

Correlation Heatmap - Feature correlations with target

Load Type Comparison - Average consumption by load category

Hourly Patterns - Energy usage by hour of day

Model Comparison - Bar chart of RMSE across models

Predicted vs Actual - Scatter plot for best model

Residual Analysis - Error distribution and Q-Q plot

Feature Importance - Top features for tree-based models
📝 Results Summary
Key Business Implications
Area	Impact
Operational Planning	Accurate energy forecasting (RMSE ~2.9 kWh)
Cost Optimization	Identify peak usage periods to reduce demand charges
Sustainability	Track CO₂ emissions through energy consumption
Process Optimization	Load type analysis for production scheduling
📚 Learnings
Technical Skills Developed
✅ Data cleaning and feature engineering

✅ Exploratory data analysis with visualizations

✅ Implementation of multiple regression models

✅ Model evaluation and comparison

✅ Cross-validation and overfitting detection

✅ Feature importance analysis

Domain Insights
Industrial energy consumption follows predictable patterns

Non-linear models are essential for accurate predictions

CO₂ emissions are a reliable proxy for energy usage

Load type and time of day are critical factors
🙏 Acknowledgments
Dataset: UCI Machine Learning Repository

Framework: Scikit-learn documentation and community

Inspiration: Real-world industrial data science applications


📊 Project Status
✅ Completed

EDA with Feature Engineering

Model Training and Evaluation

Model Selection and Analysis

⏳ Future Work

Hyperparameter Optimization

Model Deployment
