# Water Potability Analysis


## 📝 Problem Statement

Access to clean drinking water is a critical global challenge. This project analyzes water quality data to identify the key factors that determine whether water is potable (safe for human consumption) or not.

The dataset contains measurements of 9 water quality parameters:
- **pH**: Acidity/alkalinity level
- **Hardness**: Mineral content (calcium and magnesium)
- **Solids**: Total dissolved solids
- **Chloramines**: Disinfectant residual
- **Sulfate**: Naturally occurring mineral
- **Conductivity**: Electrical conductivity (indicator of dissolved ions)
- **Organic Carbon**: Organic matter content
- **Trihalomethanes**: Disinfection byproducts
- **Turbidity**: Water clarity

The target variable **Potability** indicates whether the water is safe to drink (1) or not (0).

## 🎯 Project Goals

| Goal | Description | Outcome |
|------|-------------|---------|
| **1. Identify Key Drivers** | Determine which parameters most influence potability | Insights on feature importance |
| **2. Segment Water Sources** | Group similar water samples by quality parameters | Natural clusters of water quality |

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Python (pandas, numpy, matplotlib, seaborn)** | Data cleaning, exploratory analysis, and visualization |
| **Jupyter Notebook** | Interactive environment for analysis and documentation |
| **Tableau** | Dashboard creation and visualization |
| **GitHub** | Version control and portfolio hosting |

---

## 📂 Dataset

- **Source**: Kaggle Water Potability Dataset
- **Rows**: 2620 (1617 after cleaning)
- **Columns**: 10 (9 features + 1 target)
- **Target**: Potability (1 = potable, 0 = not potable)

---

## 📂 Steps Followed

### 1. Data Cleaning

**Purpose**: Prepare the dataset for analysis by handling missing values and outliers.

**Key Actions**:
- Identified missing values in `Sulfate` (23.7%), `pH` (14.7%), and `Trihalomethanes` (4.8%)
- Dropped rows with missing values to maintain clean, complete data
- Capped outliers at the 99th percentile to prevent distortion of visualizations
- Verified no missing values remained after cleaning

**Decision**: Rows with missing values were dropped because the dataset contained sufficient rows (2620) to support this approach. This project focuses on exploratory analysis and visualization — not model training.

---

### 2. Exploratory Data Analysis (EDA)

**Purpose**: Understand the distribution, spread, and relationships between water quality parameters.

**Key Actions**:
- Generated summary statistics for all parameters
- Created histograms to visualize parameter distributions
- Built boxplots to compare parameters by potability
- Calculated correlation matrix to identify relationships

**Key Observations**:
- **pH**: Approximately normal distribution centered around 7.0
- **Solids**: Highly right-skewed — most samples have low solids, with some extreme values
- **Potability**: Only ~38% of samples are potable — a significant class imbalance
- **Solids and Conductivity**: Strong positive correlation (as solids increase, conductivity increases)
- **pH and Chloramines**: Moderate negative correlation (higher pH = lower chloramines)

*![Correlation Heatmap](https://github.com/user-attachments/assets/bd631db0-40c5-4cc7-930b-3b1010302e19)*

---

### 3. Data Visualization (Tableau)

**Purpose**: Create an interactive dashboard to explore water quality patterns and potability drivers.

**Dashboard 1: Overview & Comparisons**
- KPI Cards: Total Samples, Potable %, Average pH, Average Turbidity
- Donut Chart: Potability breakdown (38% potable, 62% non-potable)
- Boxplots: pH and Turbidity by Potability

**Dashboard 2: Relationships & Distributions**
- Scatter Plots:
  - Solids vs. Conductivity (strong positive correlation)
  - pH vs. Chloramines (moderate negative correlation)
  - Organic Carbon vs. Trihalomethanes (potential relationship)
- Histograms: All 9 water quality parameters

*![Dashboard Overview](https://github.com/user-attachments/assets/116b0652-351d-4a60-bd58-c92afdb247f9)*

---

## 🔍 Key Insights

| Insight | Finding |
|---------|---------|
| **Potability Imbalance** | Only 38% of water samples are potable — highlighting the importance of water treatment |
| **Key Drivers** | pH and Turbidity show the clearest differences between potable and non-potable samples |
| **Correlations** | Solids and Conductivity are strongly correlated (R² = 0.89) |
| **pH Influence** | Potable water tends to have slightly higher pH (closer to neutral) |
| **Turbidity Impact** | Non-potable water has higher turbidity (cloudiness) on average |
| **Class Imbalance** | Potable samples are underrepresented — a challenge for predictive modeling |

### Histograms
![Image](https://github.com/user-attachments/assets/b8f824a9-d4a7-45a9-9b1a-6ca8dabbd8d1)

### Boxplots
![Image](https://github.com/user-attachments/assets/c30bfa83-0aeb-4736-a81a-47068d87be03)

---

## 📌 Recommendations

1. **Prioritize pH and Turbidity** as key indicators for water quality monitoring
2. **Address class imbalance** if building predictive models (consider oversampling or SMOTE)
3. **Investigate extreme outliers** — they may represent unique water sources or measurement errors
4. **Expand data collection** to include source location and treatment history
5. **Implement real-time monitoring** for pH, turbidity, and chloramines

---

## 📁 Repository Structure
├── README.md

├── water_potability_cleaning.ipynb # Jupyter Notebook with full analysis

├── water_potability_cleaned.csv # Cleaned dataset

├── water_potability.twbx # Tableau packaged workbook

├── correlation_heatmap.png
