# 🌍 Tourism Analytics Dashboard — Power BI Capstone Project
📈 Overview

This project explores global tourism data to uncover patterns, growth trends, and regional performance.
Built entirely in Power BI, the dashboard transforms raw data into clear and actionable insights that highlight tourist distribution, growth rate, travel modes, and regional analysis.

# 🧭 Project Objective

To design an interactive dashboard that helps users:

Analyze tourism growth over time

Identify top-performing continents and countries

Track visitor distribution by travel mode (Air, Land, Sea, River)

Measure key performance metrics through DAX-driven KPIs

# ⚙️ Tools and Technologies

Power BI Desktop — Dashboard design and visualization

Power Query Editor — Data cleaning and transformation

DAX (Data Analysis Expressions) — KPI and measure creation

🧹 Data Cleaning and Transformation (Power Query Techniques)

The dataset required several transformation steps before analysis.
Some key techniques applied in Power Query include:

Removed Duplicates and Null Values
Ensured data consistency by removing empty and repeated records.

Changed Data Types

Converted Year to Whole Number instead of Date to avoid 1905 errors.

Set Tourists and GDP columns to Decimal Number for accurate aggregations.

Created Derived Columns

Extracted Year and Month from date fields.

Added calculated columns for better time-based segmentation.

Replaced Missing Values
Filled missing or invalid continent names using related country data.

Standardized Text Fields
Used the Format → Capitalize Each Word transformation for readability.

# 🧮 DAX Measures and KPI Formulas
Measure Name	DAX Formula	Purpose
Total Tourists	Total Tourists = SUM(tourism_data_cleaned[Tourists])	Calculates overall tourist count
YoY Growth %	YoY Growth % = DIVIDE([Total Tourists] - CALCULATE([Total Tourists], DATEADD('Date'[Date], -1, YEAR)), CALCULATE([Total Tourists], DATEADD('Date'[Date], -1, YEAR)))	Measures year-over-year growth rate
Average Tourists per State	Avg Tourists per State = AVERAGE(tourism_data_cleaned[Tourists])	Computes average number of tourists per state
Average GDP	Average GDP = AVERAGE(tourism_data_cleaned[GDP])	Tracks mean GDP across regions
Top Continent	Top Continent = VAR TopTable = TOPN(1, SUMMARIZE(tourism_data_cleaned, tourism_data_cleaned[continent], "TotalTourists", [Total Tourists]), [TotalTourists], DESC) RETURN MAXX(TopTable, tourism_data_cleaned[continent])	Displays the continent with the highest tourist volume
# 📊 Dashboard Highlights
<img width="1450" height="759" alt="Screenshot 2025-10-26 080557" src="https://github.com/user-attachments/assets/3344ff5e-2055-45a4-bb9c-ff0a46484634" />

KPIs Displayed:

Total Tourists

YoY Growth %

Avg Tourists per State

Average GDP

Top Continent

Visuals Included:

Line chart: Total Tourists by Year

Bar chart: Count of Continents by Year

Map: Tourists by Country and State

Donut chart: Tourists by Mode of Travel

Interactive Filters: Continent, Year, State, Way_in, and Season

# 📘 Key Learnings

Importance of data type correction in Power BI to prevent aggregation errors.

Leveraging DAX to build scalable and dynamic KPIs.

Designing dashboards that balance insight, clarity, and interactivity.

# 👨‍💻 About the Author

Abhijeet Kuanr
Data Analytics Enthusiast | Power BI Developer
Passionate about transforming raw data into insights through visualization and storytelling.

🔗 [Connect to me on Linkedin](www.linkedin.com/in/abhijeet-kuanr-6a2672160/)

📂 [More Projects on GitHub](https://github.com/Abhijeet107/)

# 🏁 Conclusion

This Power BI project demonstrates the complete analytics workflow — from data cleaning and transformation to DAX-driven insights and interactive visualization.
It’s an ideal capstone for showcasing analytical thinking, dashboard design, and business intelligence skills.
