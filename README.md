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

