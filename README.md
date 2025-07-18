# 🚦 Road Accident Analysis Dashboard – Power BI

This project presents a comprehensive Power BI dashboard analyzing road accident data to uncover patterns, risks, and actionable insights. It is designed to help stakeholders, policy makers, and data analysts understand accident trends and improve road safety infrastructure.

## 📁 Dataset

**Source:** Provided in Excel format (`Road Accident Data.xlsx`)  
**Fields Include:**
- Accident Date
- Accident Severity
- Weather Conditions
- Road Surface Conditions
- Junction Control
- Police Force
- Region
- ...and more

## 📊 Dashboard Overview

The dashboard is organized into **3 interactive pages**:

### Page 1: Road Safety Overview
- KPIs: Total Accidents, Fatal, Serious, Slight, Accidents This Year
- Line Chart: Accidents Over Time
- Donut Chart: Severity Distribution
- Filters: Year, Month, Severity

### Page 2: Accident Patterns & Risk Factors
- Bar Chart: Accidents by Day of Week
- Stacked Bar: Weather Conditions vs Severity
- Clustered Bar: Road Surface vs Severity
- Matrix: Time of Day vs Day (if available)
- Filters: Weather, Road Surface, Day

### Page 3: Location & Junction Insights
- Map: Accident Locations (if lat/long available)
- Table: Top Junction Controls Contributing to Accidents
- Bar Chart: Accidents by Police Force
- Filters: Region, Junction Type, Severity

## 📈 KPIs and DAX Measures

```DAX
Total Accidents = COUNT('Accidents'[Accident_Index])
Fatal Accidents = CALCULATE([Total Accidents], 'Accidents'[Accident_Severity] = "Fatal")
Serious Accidents = CALCULATE([Total Accidents], 'Accidents'[Accident_Severity] = "Serious")
Slight Accidents = CALCULATE([Total Accidents], 'Accidents'[Accident_Severity] = "Slight")
This Year Accidents = CALCULATE([Total Accidents], YEAR('Accidents'[Accident_Date]) = YEAR(TODAY()))
