# 🌤️ Weather Trend Analysis for Sydney  
### Using SQL and Tableau (7-Year & 14-Year Moving Averages)

This project provides a detailed analysis of long-term weather trends in **Sydney, Australia** using historical data. Leveraging **SQL** for data processing and **Tableau** for visualization, we explore the shifts in weather patterns by calculating **7-year and 14-year moving averages** for temperature-related metrics.

---

## 📘 Project Overview

### Objective:
To perform an in-depth weather trend analysis to understand how climate indicators—such as average temperature—have changed in Sydney over the years.

### Key Highlights:
- SQL used to clean, aggregate, and calculate rolling averages on historical temperature data
- Tableau dashboards to visualize long-term temperature trends
- Comparison of short-term (7-year) vs long-term (14-year) moving averages

---

## 🧮 Data Processing

### Tools Used:
- **SQL** (PostgreSQL / MySQL / BigQuery, etc.) for:
  - Data cleaning and filtering
  - Grouping temperature data by year
  - Calculating moving averages using `WINDOW FUNCTIONS`

### Sample SQL Query (Rolling Average):
```sql
SELECT
    year,
    AVG(avg_temperature) AS yearly_avg_temp,
    AVG(AVG(avg_temperature)) OVER (ORDER BY year ROWS BETWEEN 6 PRECEDING AND CURRENT ROW) AS avg_temp_7yr,
    AVG(AVG(avg_temperature)) OVER (ORDER BY year ROWS BETWEEN 13 PRECEDING AND CURRENT ROW) AS avg_temp_14yr
FROM
    weather_data
WHERE
    city = 'Sydney'
GROUP BY
    year
ORDER BY
    year;
```

### 📊 Visualization with Tableau

A dynamic Tableau dashboard was developed to:

Show trends of average yearly temperatures

Overlay 7-year and 14-year moving average curves

Provide interactive year filters for historical comparisons

Highlight any visible signs of long-term climate change

### Key Dashboard Features:

Line Charts for temperature trends and moving averages

Tooltips showing yearly statistics

Interactive Filters for year selection

Annotations to indicate weather anomalies or changes

### 🧠 Insights

Both 7-year and 14-year moving averages show a gradual increase in average temperature over the past decades

Short-term trends (7-year MA) show greater sensitivity to anomalies like heatwaves

Long-term trends (14-year MA) provide a smoother, more stable view of climate change

### 📌 Requirements

SQL engine (PostgreSQL, MySQL, or BigQuery)

Tableau Desktop (2021.1 or later recommended)

Cleaned historical weather dataset (CSV or database table)

### 👤 Author
Waqar Ahmed
📧 waqar.nu@gmail.com
🔗 [https://github.com/waqar-ahmed91/Weather-Trend-Analysis/]GitHub

📜 License
This project is for educational and analytical purposes only. Data sources must be credited accordingly if reused.

