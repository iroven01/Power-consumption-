# Power-consumption-
# ⚡ Tetouan City Power Consumption Analysis

## 📌 Project Overview

This project performs a comprehensive **Exploratory Data Analysis (EDA)** 
on the Tetouan City Power Consumption dataset. The dataset records electrical 
power consumption across **three distribution zones** in Tetouan, Morocco, 
at **10-minute intervals** throughout the year 2017.

The analysis aims to uncover consumption patterns, identify peak hours, 
detect anomalies, and understand the relationship between weather conditions 
and power usage — with findings visualized in an interactive **Power BI dashboard**.

---

## 📂 Project Structure
---

## 📊 Dataset Information

| Feature | Description |
|---|---|
| **Source** | UCI Machine Learning Repository |
| **Location** | Tetouan City, Morocco |
| **Period** | January 2017 – December 2017 |
| **Frequency** | Every 10 minutes |
| **Total Records** | 52,416 rows |
| **Features** | 9 columns |

### Features Description

| Column | Type | Description |
|---|---|---|
| Datetime | DateTime | Timestamp of recording |
| Temp_°C | Float | Ambient temperature in Celsius |
| Humidity | Float | Relative humidity (%) |
| Windspeed | Float | Wind speed (m/s) |
| General_Diffuse_Flows | Float | Solar diffuse radiation |
| Diffuse_Flows | Float | Direct diffuse radiation |
| Power_Consumption_kWh_Zone1 | Float | Zone 1 power consumption |
| Power_Consumption_kWh_Zone2 | Float | Zone 2 power consumption |
| Power_Consumption_kWh_Zone3 | Float | Zone 3 power consumption |

---

## 🎯 Project Objectives

- ✅ Perform full **Exploratory Data Analysis** on power consumption data
- ✅ Analyze **univariate distributions** of all numerical and categorical features
- ✅ Investigate **bivariate relationships** between weather and consumption
- ✅ Identify **peak consumption hours, days and months**
- ✅ Compare consumption patterns across **three distribution zones**
- ⬜ Time Series Analysis *(upcoming)*
- ⬜ Consumption Forecasting *(upcoming)*

---

## 🔍 Key Findings

### 📌 Univariate Analysis
- **Temperature** follows a near-normal distribution (mean: 18.81°C)
  confirming all four seasons are captured
- **Windspeed** shows a bimodal distribution — city experiences 
  either very calm or notably windy conditions
- **Solar flow variables** are heavily right-skewed with high kurtosis,
  consistent with zero radiation at night and peaks during the day
- **Zone 1** is the largest consumer (mean: 32,344 kWh) and most stable
- **Zone 3** is the most volatile zone with highest skew (1.02)

### 📌 Bivariate Analysis
- **Weekdays consistently show higher consumption** than weekends
  across all zones — suggesting residential/commercial dominant usage
- **Summer (August) and Winter (January)** are peak consumption months —
  classic bimodal seasonal pattern driven by cooling and heating loads
- **Temperature correlates positively** with all three zones:
  - Zone 1: r = 0.49 (Moderate)
  - Zone 2: r = 0.34 (Weak-Moderate)
  - Zone 3: r = 0.41 (Moderate)
- **Zone vs Zone comparison** shows all three zones rise and fall together,
  confirming they are driven by the same external factors

### 📌 Zone Characteristics
| Zone | Avg Consumption | Behavior | Likely Area Type |
|---|---|---|---|
| Zone 1 | 32,344 kWh | Stable, largest | Industrial/Large Commercial |
| Zone 2 | 21,042 kWh | Most consistent | Mixed Residential/Commercial |
| Zone 3 | 17,835 kWh | Most volatile | Residential/Seasonal |

---

## 🛠️ Technologies Used

```python
# Data Manipulation
import pandas as pd
import numpy as np

# Visualization
import matplotlib.pyplot as plt
import seaborn as sns
```

---

## 🚀 How to Run

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Steps
```bash
# 1. Clone the repository
git clone https://github.com/yourusername/tetouan-power-consumption.git

# 2. Navigate to project folder
cd tetouan-power-consumption

# 3. Launch Jupyter Notebook
jupyter notebook consumption.ipynb
```

### Data Processing Pipeline
```python
# The notebook follows this pipeline:

Raw Data (10-min intervals)
        ↓
Data Cleaning & Type Conversion
        ↓
Feature Engineering (Month, Day, Hour)
        ↓
├── df_hourly    → iloc[::6] every 6th row
├── df_resampled → hourly mean
└── df_daily     → hourly then daily sum
        ↓
Univariate Analysis
        ↓
Bivariate Analysis
```

----

## 📋 Analysis Workflow
---

## 🔮 Future Work

- [ ] **Time Series Decomposition** — trend, seasonality, noise
- [ ] **Stationarity Testing** — ADF test before modeling
- [ ] **SARIMA Modeling** — classical forecasting approach
- [ ] **Prophet Forecasting** — handling multiple seasonalities
- [ ] **Anomaly Detection** — Z-score based spike detection
- [ ] **Clustering** — group similar consumption hours

---

## 👤 Author

Okwara Iroha Uko
- 🎓 Data Analyst | Electrical Engineer
- 📧 Email: okwarachibueze2@gmail.com
- 💼 LinkedIn: https://www.linkedin.com/in/iroha-okwara?utm_source=share_via&utm_content=profile&utm_medium=member_android

---


## 🙏 Acknowledgements

- Dataset sourced from the 
  **[UCI Machine Learning Repository](https://archive.ics.uci.edu/)**
- Tetouan City power distribution data provided for research purposes

---

⭐ **If you found this project helpful, please give it a star!** ⭐
