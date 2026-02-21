# Renewable-Energy-Consumption-Trends
The project analyses Renewable Energy consumption from 1970 to 2023, and presents the results in an Interactive Power BI dashboard, to help understand how energy consumption has evolved over time.

## 📌 Project Overview
Governments and policymakers rely on long-term renewable energy data to inform infrastructure investment, sustainability targets, and energy diversification strategies. Understanding how renewable energy consumption has evolved over time and which sectors and energy sources dominate which is critical for supporting the transition to a resilient, diversified energy system. 

## 📌 Exploratory Data Analysis (EDA)
Before building the visuals, I explored the dataset directly to understand its structure, completeness in power query. Reviewed the dataset for missing, null, or zero values that could distort aggregations or trends, there were no missing values present. The original dataset was in a wide format, to make the data suitable for analysis I unpivoted all columns, retaining only  (Year, Month, Sector). This transformation normalised the dataset into a long format, enabling aggregation, filtering.

## 📌 DAX Measures Used
o implement the analytical logic, I wrote DAX measures to aggregate and rank consumption values dynamically.

1. The core measure, Total Energy Consumption, sums renewable energy use across all records and forms the basis for trend analysis, rankings, and KPIs
2. A measure Top Renewable Source summarises consumption by energy source and returning the highest contributor within the current filter context
3. Implemented context-aware measures to ensure all visuals respond accurately to slicer selections. 
 

## 📌 Model
The model consists of a central fact table linked to a dedicated date table. This simple dimensional structure enables accurate time-based aggregation and responsive filtering across the dashboard.

<p align="center">
  <img src="Screenshot 2026-02-21 at 13.15.28.png"250"/>
</p>

## 📌 Key Measures and Calculations
Total Transaction Amount - This measure calculates the total value of all transactions

```DAX
Total Transaction Amount = SUM('bank transaction_data'[Transaction Amount])
```

```DAX
Total Transactions = DISTINCTCOUNT('bank transaction_data'[Transaction ID])
```

```DAX
Bandwidth Group = SWITCH ( TRUE(), [Slice Bandwidth (Mbps)] >= 50 && [Slice Bandwidth (Mbps)] < 100, "50–100 Mbps", [Slice Bandwidth (Mbps)] >= 100 && [Slice Bandwidth (Mbps)] < 150, "100–150 Mbps", [Slice Bandwidth (Mbps)] >= 150 && [Slice Bandwidth (Mbps)] <= 250, "150–250 Mbps", "Out of Range" )
```

## 🛠️ Tools Used
Power BI for data modelling, visualisation, and dashboard development
DAX for calculated measures and bandwidth grouping

## 📌 Dashboard Design and Exploration
The dashboard is structured to move from high-level performance metrics to more detailed analysis. Summary KPIs provide immediate visibility into transaction volume and value, while bandwidth group visuals highlight how activity is distributed across network capacity tiers. Interactive filters allow users to drill into specific transaction segments and explore patterns in more detail.

## 📌 Key Insights
The dashboard shows 1,000 transactions with a total value of approximately £771K. Transaction outcomes are almost evenly split, with 513 failed and 487 successful transactions, highlighting potential reliability issues within the transaction process. Transaction activity is most concentrated in the 150–250 Mbps bandwidth group, which records the highest volume of transactions. Lower bandwidth ranges handle fewer transactions, indicating that higher network capacity supports the bulk of processing. Transaction types are evenly distributed, with Transfers (37.4%), Deposits (31.6%), and Withdrawals (31%), suggesting no single transaction type disproportionately drives system load. Fraud-flagged transactions account for just over half of total activity (51.9%) and are again most concentrated in the 150–250 Mbps bandwidth tier, reinforcing the link between higher bandwidth usage and increased risk. Transaction and fraud activity are primarily concentrated in North America and Europe.

## 📌 Business Value
The concentration of activity and fraud in the 150–250 Mbps range highlights this tier as a priority for capacity planning, monitoring, and optimisation. The high proportion of failed transactions indicates areas where performance improvements could significantly increase system reliability. By linking transaction value, bandwidth usage, and fraud indicators, the dashboard supports targeted risk monitoring and more efficient allocation of infrastructure resources. 

## 📌 Conclusion
This project demonstrates how combining transaction metrics with bandwidth analysis can reveal where system demand and risk are highest. The Power BI dashboard provides a clear, practical view of transaction performance, supporting better operational monitoring and informed decisions around network capacity and fraud control.

Interact with the dashboard - https://app.powerbi.com/groups/me/reports/2e0b58a6-e735-4c45-92f4-31a6c571e1d5/d74678b5934723b76859?experience=power-bi


<p align="center">
  <img src="Screenshot 2026-02-21 at 13.15.28.png"250"/>
</p>

<p align="center">
  <img src="Screenshot 2026-02-21 at 13.15.37.png"250"/>
</p>

<p align="center">
  <img src="Screenshot 2026-02-21 at 13.15.45.png"250"/>
</p>
