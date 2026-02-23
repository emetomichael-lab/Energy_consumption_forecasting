# ⚡ Energy Consumption Forecasting

> **Time-series forecasting of 300 hourly energy records across 6 energy types and 5 UK regions**  
> Built as part of Michael Emeto's Data Analytics Portfolio — MSc Data Analytics, BPP University Manchester

---

## 📌 Project Overview

This project models hourly energy consumption patterns, identifies seasonal and weather-driven demand drivers, and builds a **30-day demand forecast** using Facebook Prophet. It targets a critical operational challenge for grid operators: anticipating demand spikes to prevent blackouts and minimise costly emergency imports.

The analysis covers Solar, Wind, Gas, Nuclear, Hydro, and Coal energy types across five UK regions.

---

## 📊 Key Results

| Metric | Value |
|--------|-------|
| Forecast Accuracy | **91%** |
| Prophet MAE | **12.3 kWh** |
| ARIMA MAE (Baseline) | 18.7 kWh |
| Model Improvement | **+34% over ARIMA** |
| Dataset Size | 300 hourly records |
| Energy Types | 6 (Solar, Wind, Gas, Nuclear, Hydro, Coal) |

---

## 💡 Key Findings

- **Solar irradiance** has a correlation of **r = −0.71** with grid imports — the most powerful single factor for reducing grid dependency
- Temperatures below **5°C** drive a **38% average consumption increase**
- **Wind energy** costs £0.09/kWh vs Coal at £0.28/kWh — a **211% price difference**
- **Weekend demand** averages 17% lower than weekdays — a predictable maintenance window
- Just **8% of daily hours** (6–9am, 5–8pm) account for **31% of annual consumption**
- Facebook Prophet outperformed ARIMA by **34%** on MAE

---

## 🛠️ Technologies Used

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Prophet](https://img.shields.io/badge/Facebook%20Prophet-Forecasting-0668E1)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?logo=pandas)
![SciPy](https://img.shields.io/badge/SciPy-Correlation%20Analysis-8CAAE6)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi)
![Excel](https://img.shields.io/badge/Excel-Dataset-217346?logo=microsoftexcel)

---

## 📁 Project Structure

```
energy-consumption-forecasting/
│
├── energy_consumption_forecasting.py   # Main analysis & forecasting pipeline
├── energy_analysis.xlsx                # Dataset (300 hourly energy records)
├── energy_by_type.png                  # Consumption by energy type chart
├── energy_forecast.png                 # 30-day Prophet forecast plot
├── energy_components.png               # Seasonality components decomposition
├── energy_cost.png                     # Cost comparison by energy type
└── README.md
```

---

## ⚙️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/michael-emeto/energy-consumption-forecasting.git
cd energy-consumption-forecasting
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn prophet scipy openpyxl scikit-learn
```

### 3. Run the analysis
```bash
python energy_consumption_forecasting.py
```

> ✅ Make sure `energy_analysis.xlsx` is in the same directory as the script.

---

## 📋 Dataset Features

| Feature | Type | Description |
|---------|------|-------------|
| `Temperature_C` | Numeric | Ambient temperature in Celsius |
| `Solar_Irradiance` | Numeric | Solar irradiance (W/m²) |
| `Wind_Speed_ms` | Numeric | Wind speed in metres per second |
| `Energy_Type` | Categorical | Solar, Wind, Gas, Nuclear, Hydro, Coal |
| `Consumption_kWh` | Numeric | Hourly consumption in kilowatt-hours |
| `Grid_Import_kWh` | Numeric | Grid import requirement |
| `Day_Type` | Engineered | Weekday vs Weekend classification |

---

## 📈 Methodology

1. **Data Parsing** — Combined Date + Hour columns into full datetime index
2. **Correlation Analysis** — Pearson r for weather variables vs consumption targets
3. **Daily Aggregation** — Summed hourly to daily for Prophet compatibility
4. **Prophet Modelling** — Multiplicative seasonality, yearly + weekly components
5. **Model Comparison** — Prophet vs ARIMA(2,1,2) vs Holt-Winters
6. **30-Day Forecast** — Future demand predictions with confidence intervals

---

## 👤 Author

**Michael Emeto** — Data Analyst | Manchester, UK  
📧 Emetomichael@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/michael-emeto)  
🎓 MSc Management in Data Analytics — BPP University (2025–2026)

---

## 📄 License

This project is for portfolio and educational purposes.
[README_energy.md](https://github.com/user-attachments/files/25496816/README_energy.md)
