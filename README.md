# Renewable-Energy-Consumption-Trends
The project analyses Renewable Energy consumption from 1970 to 2023, and presents the results in an Interactive Power BI dashboard, to help understand how energy consumption has evolved over time.

## 📌 Project Overview
Governments and policymakers rely on long-term renewable energy data to inform infrastructure investment, sustainability targets, and energy diversification strategies. Understanding how renewable energy consumption has evolved over time and which sectors and energy sources dominate which is critical for supporting the transition to a resilient, diversified energy system. 

## 📌 Exploratory Data Analysis (EDA)
Before building the visuals, I explored the dataset directly to understand its structure, completeness in power query. Reviewed the dataset for missing, null, or zero values that could distort aggregations or trends, there were no missing values present. The original dataset was in a wide format, to make the data suitable for analysis I unpivoted all columns, retaining only  (Year, Month, Sector). This transformation normalised the dataset into a long format, enabling aggregation, filtering.

## 📌 DAX Measures Used
To implement the analytical logic, I wrote DAX measures to aggregate and rank consumption values dynamically.

## 📌 Model
The model consists of a central fact table linked to a dedicated date table. This simple dimensional structure enables accurate time-based aggregation and responsive filtering across the dashboard.

1. The core measure, Total Energy Consumption, sums renewable energy use across all records and forms the basis for trend analysis, rankings, and KPIs
2. A measure Top Renewable Source summarises consumption by energy source and returning the highest contributor within the current filter context
3. Implemented context-aware measures to ensure all visuals respond accurately to slicer selections. 
 
## 📌 Results
1. KPI Summary - There are three essential Key Performance Indicators (KPIs) displayed as card visuals in PowerBI with contextual labelling to support quick decision-making.
A. Total Energy Consumption (TBTUs) – shows the total 384.04K TBTUs of renewable energy use from 1970-2023
B. Top Renewable Source – identifies the leading energy source by consumption volume
C. Dominant Sector – highlights the sector driving the majority of renewable energy demand

2. Trend Analysis
The long-term trend shows three clear phases in renewable energy consumption. Between 1970 and 1990, consumption remained largely flat, indicating limited policy and technological support. From 1990 to 2010, consumption increased steadily, reaching around 8,000 TBTUs by 2010 as early incentives emerged. After 2010, growth accelerated sharply, rising to over 12,500 TBTUs by 2023—a 56% increase in 13 years and a 257% increase overall since 1970.

3. Sector Composition
The top three sectors (Industrial, Electric Power, and Transportation) account for 88.93% of all renewable energy consumption. This indicates that while renewable energy deployment is widespread, adoption is unevenly distributed.

4. Renewable Energy Source Ranking
Biomass and Wood Energy together account for 66.1% (254.19K TBTUs) of all renewable energy consumption. The top three sources represent 78.7% of total consumption, indicating strong concentration in established renewable technologies.

## 📌 Interpretation
US renewable energy consumption has shifted from slow growth to rapid expansion since 2010, increasing by 56% in the past decade. Consumption is heavily concentrated in three sectors which are ndustrial, electric power and transportation, they account for 88.93% of total use, while residential and commercial adoption remains limited. Biomass and wood energy dominate the mix at 66.1%, highlighting reliance on established technologies and limited diversification into newer renewable sources.

## 🛠️ Conclusion and Recommendation
Renewable energy growth requires greater diversification, as biomass accounts for 66.1% of consumption. Increased investment in solar, wind and geothermal energy, alongside targeted incentives for residential and commercial adoption, would improve system resilience while maintaining support for high-consumption sectors. With consumption growing 56% since 2010, continued monitoring and long-term planning are essential to sustain progress.

Interact with the dashboard - [https://app.powerbi.com/groups/me/reports/2e0b58a6-e735-4c45-92f4-31a6c571e1d5/d74678b5934723b76859?experience=power-bi](https://app.powerbi.com/groups/me/reports/e6e6151f-b33c-42bd-b886-d4f8dc4122af/dbe1b43f1b5a9fa3b247?experience=power-bi)


<p align="center">
  <img src="Screenshot 2026-02-21 at 13.31.55.png"250"/>
</p>

