# 🌍 COVID-19 Data Exploration

### 📊 Global COVID-19 Spread & Impact Analysis using Python & SQL

---

## 🧠 **Project Overview**

This project focuses on exploring and analyzing the **global spread and impact of COVID-19** using **SQL** for data querying and **Python** for data visualization and analysis.

The goal is to gain insights into:
- 🌎 Global infection and death trends  
- 🏳️‍🌈 Top affected countries  
- ⚰️ Death and recovery rates  
- 📈 Time-series changes in infection rates  

---

## 🎯 **Objectives**

- Store and manage COVID-19 data in a relational database (SQL)  
- Perform data exploration using SQL queries  
- Visualize infection trends using Python (Matplotlib, Plotly)  
- Generate insights from the global COVID dataset  

---

## 🧩 **Tools & Technologies**

| Category | Tools Used |
|-----------|-------------|
| Database | MySQL / SQLite |
| Data Analysis | Python (Pandas) |
| Visualization | Matplotlib, Plotly |
| IDE | Jupyter Notebook / VS Code |
| Dataset | COVID-19 World Dataset (Kaggle / Our World in Data) |

---

## 📂 **Dataset Description**

| Column Name | Description |
|--------------|--------------|
| `date` | Date of the record |
| `country` | Country name |
| `confirmed` | Total confirmed cases |
| `deaths` | Total death count |
| `recovered` | Total recovered cases |
| `population` | Population of the country |
| `new_cases` | Daily new cases |
| `new_deaths` | Daily new deaths |

---

## ⚙️ **Project Workflow**

### 🧾 Step 1: Data Collection & Preparation
- Download COVID-19 dataset from Kaggle / Our World in Data  
- Clean and preprocess data (handle missing values, remove duplicates)

### 🗄️ Step 2: Database Setup (SQL)
- Create a database `covid_project`
- Create a table `covid_data`
- Import CSV data into SQL

**Sample Table:**
```sql
CREATE TABLE covid_data (
    date DATE,
    country VARCHAR(100),
    confirmed INT,
    deaths INT,
    recovered INT,
    population INT,
    new_cases INT,
    new_deaths INT
);
```
### 🧮 Step 3: SQL Data Analysis

```
-- Top 10 countries by confirmed cases
SELECT country, MAX(confirmed) AS Total_Confirmed
FROM covid_data
GROUP BY country
ORDER BY Total_Confirmed DESC
LIMIT 10;

-- Death rate per country
SELECT country,
       ROUND(MAX(deaths)/MAX(confirmed)*100, 2) AS Death_Rate
FROM covid_data
GROUP BY country
ORDER BY Death_Rate DESC;
```
### 🐍 Step 4: Python Data Analysis
```
import pandas as pd
import matplotlib.pyplot as plt
import plotly.express as px
import mysql.connector

conn = mysql.connector.connect(
    host='localhost',
    user='root',
    password='your_password',
    database='covid_project'
)

query = "SELECT * FROM covid_data"
df = pd.read_sql(query, conn)
```
### 📊 Step 5: Visualization

```
# Top 10 countries by confirmed cases
top_countries = (
    df.groupby('country')['confirmed']
    .max()
    .sort_values(ascending=False)
    .head(10)
    .reset_index()
)

fig = px.bar(top_countries, x='country', y='confirmed',
             title='Top 10 Countries by Confirmed Cases',
             color='confirmed', text='confirmed')
fig.show()
```
### 🧠 Step 6: Insights & Conclusion

- India, USA, and Brazil show the highest infection rates

- Death rates vary significantly between regions

- The global trend shows waves of increase & decline in cases

### 🧾 Project Tasks  

| Task              | Description                                   |
| ----------------- | --------------------------------------------- |
| ✅ Data Collection | Collect dataset from Kaggle or public sources |
| ✅ SQL Setup       | Create database and import data               |
| ✅ Querying        | Write SQL queries for analysis                |
| ✅ Data Analysis   | Analyze trends with Pandas                    |
| ✅ Visualization   | Plot charts with Matplotlib & Plotly          |
| ✅ Reporting       | Summarize key insights and findings           |

### 📈 Expected Outputs

- SQL tables showing top affected countries

- Interactive charts for:

- Global infection trends

- Country-wise infection growth

- Death & recovery rate comparisons

---

### 🚀 Future Improvements

- 🌐 Interactive dashboard using Streamlit / Plotly Dash

- 🤖 Forecasting future cases using ARIMA or LSTM

- 🗺️ Geo-map visualization of country-wise spread

   ---

### 📁 Project Structure

```
COVID19_Data_Exploration/
│
├── dataset/
│   └── covid_data.csv
│
├── sql/
│   ├── create_table.sql
│   ├── queries.sql
│
├── python/
│   ├── covid_analysis.py
│   └── visualization.ipynb
│
├── report/
│   └── COVID19_Data_Exploration_Report.docx
│
└── README.md
```
---

### 🤝 Collaboration & Credits

👨‍💻 Developed by:

### 👥 Collaborators
- [**Wahid Vinchenzo**](https://github.com/Wahid-vinchenzo) 🇧🇩 — Project Lead, Data & SQL Analysis  
- [**MiNa Rizk**](https://github.com/MiNa-CS) 🇪🇬 — Visualization & Insight Development


✨ An international collaboration project combining data analysis, visualization, and teamwork across borders.

### 💬 Contact

If you have suggestions, improvements, or ideas, feel free to connect with us via GitHub!

### 📩 Pull requests and issues are welcome.

### 🏁 License
This project is open source and available under the MIT License
