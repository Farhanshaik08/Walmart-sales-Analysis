# Walmart Store Sales Analysis Dashboard

An interactive Power BI dashboard analysing weekly sales across 45 Walmart stores and 81 departments (2010-2012), built to surface store- and department-level trends for inventory and staffing decisions.

[Dashboard overview](Walmart%20Dashboard.png)

## Business question
How do holidays, store type and department affect weekly sales, and where should inventory and staffing be focused?

## Key findings
- **Holiday weeks lift average weekly sales by 7.1%** ($17,036 vs $15,901 in normal weeks).
- **Type A stores average about $20,100 per week**, over 2x Type C stores (about $9,520).
- Sales spike sharply around Thanksgiving and Christmas each year.
- Stores 20, 4 and 14 and Departments 92, 95 and 38 generate the most total sales.

**Recommendation:** increase inventory and staffing ahead of holiday weeks, prioritising Type A stores and the top-selling departments.

## Dataset

- 421,570 weekly sales records, 45 stores, 81 departments, 2010-2012
- Merged with store metadata (type, size) and macroeconomic indicators (CPI, unemployment, fuel price)
- Source:(https://www.kaggle.com/datasets/gustavoserafim/walmart-recruiting-store-sales-forecasting-gsr?select=train.csv)

## Data preparation

- Merged sales, store and economic-indicator tables into one clean file
- Cleaned and imputed missing values in the promotional markdown fields (50-64% incomplete across 5 columns)


## Dashboard contents

- KPI cards: Holiday Avg, Non-Holiday Avg, Holiday Lift %
- Average weekly sales by store type
- Holiday vs normal week comparison
- Weekly sales trend (2010-2012)
- Top 10 stores and top 10 departments by total sales
- Slicers for store type and month

## Tools

Power BI (DAX measures, data modelling, visualisation)

## DAX measures used

```
Total Sales = SUM(walmart_clean[Weekly_Sales])
Avg Weekly Sales = AVERAGE(walmart_clean[Weekly_Sales])
Holiday Avg = CALCULATE([Avg Weekly Sales], walmart_clean[Week_Type] = "Holiday week")
Non-Holiday Avg = CALCULATE([Avg Weekly Sales], walmart_clean[Week_Type] = "Normal week")
Holiday Lift % = DIVIDE([Holiday Avg] - [Non-Holiday Avg], [Non-Holiday Avg])
```

## Files

- `Walmart Dashboard.pbix`: Power BI file. Download it and open it in Power BI Desktop to explore the interactive version.
- `Walmart Dashboard.png`: dashboard screenshot

## Author

Farhan Shaik | [LinkedIn](https://linkedin.com/in/farhanshaik08)
