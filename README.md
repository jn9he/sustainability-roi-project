# Project Background

Comprehensive synthetic dataset based on a real university's operational energy management data: Time-series energy consumption by building, carbon emissions, project initiatives, utilityCosts, weatherData, building use/materials information, and occupancy data, incorporating data messiness to mirror actual building performance / sustainability investment data.

An interactive powerBI dashboard can be found [here]()

# Table of Contents
<a id='table_of_contents'></a><br>
[Project Summary](#section_1)<br>
[Part 1: Trends (Excel)](#section_2)<br>
[Part 2: Targeted Insights (SQL)](#section_3)<br>
[Part 3: Visualizations (Tableau)](#section_4)<br>
[Part 4: Recommendations & Next Steps](#section_5)<br>
[Addendum: Notes on Data Cleaning](#section_6)<br>

# Project Summary
 
The dataset used in this project is synthetic, generated to preserve realistic patterns, trends, and inconsistencies. 

**Stakeholder Scenario:** You're working with State University's Facilities Management and Campus Sustainability Office to create a powerBI ROI dashboard that tracks the financial and environmental impact of sustainability investments. The VP of Operations needs clear metrics to justify budget allocations and demonstrate progress toward the university's carbon neutrality goals.

**Key Business Challenge:** $2.3M invested in sustainability initiatives over 2 years with unclear ROI visibility, making it difficult to secure additional funding and optimize resource allocation.

Insights and recommendations are provided on the following key areas:

**Part 1: Trends**
 - Using Excel to take a high-level look at broad operational and environmental trends within the data to identify notable insights for the facilities, finance, and sustainability teams.

Part 2: **Insights**
- With the aid of SQL, extract targeted insights for university decision-makers, such as the performance of solar panel installations, recycling participation rates, and cost-effectiveness of green infrastructure projects.

Part 3: **Visualizations**
- Leveraging powerBI create an interactive dashboard for facilities, finance, and sustainability teams (as well as campus leadership) to monitor key performance indicators on an ongoing basis.

Part 4: **Recommendations & Next Steps**
-  Actionable suggestions for future sustainability initiatives, funding allocations, and operational improvements to enhance ROI and environmental impact.

The basic cleaning scripts and inspection of the data [here]()

**Entity Relationship Diagram (ERD):  **** <img width="1247" height="926" alt="image" src="https://github.com/user-attachments/assets/e86ab539-625b-4ad1-a524-ab119bf1df53" />

[](https://github.com/AnalyticsAccelerator/sample_repo#data-structure--initial-checks)


# Executive Summary
**Concentrated performance risk and savings opportunity**

- A small set of buildings consistently underperform across multiple intensities (worst decile on two or more metrics). These are your prime ROI targets for audits, controls tuning, and capital upgrades. Addressing just this cohort is likely to yield a disproportionate share of savings with clear, measurable impacts.

**Seasonal drivers dominate budgets**

- Portfolio energy shows clear seasonality closely tied to weather. Expect electricity to carry steady base load while winter therms spike, driving variance. Budgeting and procurement should emphasize hedging or pre-buy strategies for heating months and align maintenance windows before seasonal peaks.

**Intensity spreads signal uneven operational discipline**

- Wide spreads in kWh/sqft and water/sqft across buildings point to differences in schedules, setpoints, and equipment health. Sites with weak occupancy-to-load coupling likely have after-hours or static schedules. Tightening controls and aligning with occupancy can reduce baseline without capex.


[](https://github.com/AnalyticsAccelerator/sample_repo#executive-summary)

### Overview of Findings

[](https://github.com/AnalyticsAccelerator/sample_repo#overview-of-findings)

Explain the overarching findings, trends, and themes in 2-3 sentences here. This section should address the question: "If a stakeholder were to take away 3 main insights from your project, what are the most important things they should know?" You can put yourself in the shoes of a specific stakeholder - for example, a marketing manager or finance director - to think creatively about this section.

[Visualization, including a graph of overall trends or snapshot of a dashboard]

# Insights Deep Dive

[](https://github.com/AnalyticsAccelerator/sample_repo#insights-deep-dive)

### **Part 1: Initial Broader Trends (Excel):**

need to replace this with analysis done on cleaned data

#### 1- Utility Costs Overview

analysis_summary.csv

- **Date Range**: Utility costs data spans from **January 2022 to December 2025**.
- **Total Amount**: The total amount paid for utilities ranged from a minimum of **-$184.66** to a maximum of **$238,657.32**, with an average of **$57,102.68**. The negative minimum suggests potential credits or adjustments.
- **Rates and Charges**:
    - **Electricity Rate**: Averaged **$0.1387 per KWh**, ranging from **$0.1088 to $0.1821**.
    - **Gas Rate**: Averaged **$0.8981 per Therm**, ranging from **$0.7216 to $1.1436**.
    - **Demand Charge**: Averaged **$4,994.81**, with a range from **$2,243.65 to $7,917.11**.
    - **Taxes and Fees**: Averaged **$5,202.38**, with a significant range from **$112.59 to $23,958.53**.
- **Financial Adjustments**:
    - **Late Payment Fees**: A total of **$2,342.19** in late payment fees was incurred across **17 instances**, with individual fees ranging up to **$198.83**.
    - **Rebates Received**: A total of **$55,260.08** in rebates was received across **51 instances**, with individual rebates ranging up to **$1,974.36**.
- **Utility Providers**: There are **5 unique utility providers**. **Green Energy Co-op** is identified as the top provider by average total amount, with an average of **$83,567.01**.
- **Trend**: The overall trend for total utility costs is **generally decreasing**, with the average total amount dropping from **$97,373.20** in the first month to **$86,884.84** in the last month.

#### 2 - Energy Consumption Overview

- **Date Range**: Energy consumption data covers **January 1, 2022, to December 31, 2025**.
- **Consumption Metrics (Average)**:
    - **Electricity**: Averaged **1,120.72 KWh**.
    - **Natural Gas**: Averaged **173.82 Therm**.
    - **Steam**: Averaged **5,503.09 BTU**.
    - **Water**: Averaged **889.52 Gallons**.
- **Building Type Consumption**:
    - **Research** buildings had the highest average electricity consumption (**1,812.73 KWh**) and steam consumption (**5,520.85 BTU**).
    - **Dining** facilities showed the highest average natural gas consumption (**212.11 Therm**).
    - **Residential** buildings had the highest average water consumption (**954.71 Gallons**).
- **Correlations with Environmental Factors**:
    - **ElectricityKWh**: Showed a **weak negative correlation (-0.24)** with `Weather_TempF` and a **very weak positive correlation (0.01)** with `Weather_Humidity`.
    - **NaturalGasTherm**: Exhibited a **strong negative correlation (-0.73)** with `Weather_TempF` and a **very weak negative correlation (-0.00)** with `Weather_Humidity`. This suggests natural gas consumption significantly decreases as temperature rises.
- **Correlations with Occupancy Level**:
    - **ElectricityKWh**: Has a **weak positive correlation (0.21)** with `Occupancy_Level`.
    - **NaturalGasTherm**: Has a **weak positive correlation (0.23)** with `Occupancy_Level`.
    - **Water_Gallons**: Shows a **moderate positive correlation (0.33)** with `Occupancy_Level`.
    - **Steam_BTU**: Has a **very weak negative correlation (-0.00)** with `Occupancy_Level`.
- **Anomalies**: **27 instances** of negative `ElectricityKWh` values were identified, indicating potential data entry errors or specific operational scenarios.

#### 3 - Carbon Emissions Overview

- **Date Range**: Carbon emissions data spans from **January 2022 to December 2025**.
- **Emission Scopes (Average)**:
    - **Scope 1 Emissions**: Averaged **50.88 Tons CO2**.
    - **Scope 2 Emissions**: Averaged **30.18 Tons CO2**.
    - **Scope 3 Emissions**: Averaged **20.58 Tons CO2**.
- **Building Cluster Emissions**:
    - **West Campus** had the highest average Scope 1 emissions (**61.54 Tons CO2**) and Scope 3 emissions (**24.94 Tons CO2**).
    - **North Campus** recorded the highest average Scope 2 emissions (**41.09 Tons CO2**).
- **Carbon Mitigation Efforts**:
    - A total of **5,499 tons** of carbon offsets were purchased.
    - A total of **1,479 tons** of carbon credits were generated.
- **Verification Status**: The majority of emissions data is **Unverified (149 instances)**, followed by **Verified (97 instances)**, **Pending (83 instances)**, and **Unknown (55 instances)**.
- **Trend**: Total carbon emissions are **generally decreasing**, with the average total emissions falling from **230.91 tons** in the first month to **189.10 tons** in the last month.

#### Conclusion and Insights

- **Overall Positive Environmental Trend**: Both **utility costs and total carbon emissions show a general decreasing trend** over the analyzed period (2022-2025), suggesting potential improvements in operational efficiency or sustainability initiatives.
- **Energy Consumption Drivers**: Natural gas consumption is **strongly influenced by temperature**, indicating heating needs are a major factor. Electricity and water consumption show **weak to moderate positive correlations with occupancy levels**, suggesting that higher building utilization leads to increased usage of these resources.
- **Data Quality Considerations**: The presence of **negative electricity consumption values** and a significant portion of **unverified carbon emission data** highlights areas where data quality and verification processes could be improved for more accurate analysis and reporting.
- **Targeted Emission Reduction**: Different building clusters are dominant in different emission scopes (e.g., West Campus for Scope 1 and 3, North Campus for Scope 2), indicating that **emission reduction strategies should be tailored to specific building clusters** and their primary emission sources.
- **Financial Management**: While rebates received significantly offset costs, the presence of late payment fees suggests opportunities for **optimizing payment processes** to avoid unnecessary expenses. The wide range in taxes and fees also warrants further investigation into their drivers.



[Visualization specific to category 1]

### **Part 2: Targeted Insights (SQL**)

[](https://github.com/AnalyticsAccelerator/sample_repo#category-2)

- **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    
- **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    
- **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    
- **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    

[Visualization specific to category 2]

### **Part 3: PowerBI Dashboard**:

[](https://github.com/AnalyticsAccelerator/sample_repo#category-3)

- **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    
- **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    
- **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    
- **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
    

[Visualization specific to category 3]

# Recommendations:

[](https://github.com/AnalyticsAccelerator/sample_repo#recommendations)

Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following:

- Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
    
- Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
    
- Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
    
- Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
    
- Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
    

# Assumptions and Caveats:

[](https://github.com/AnalyticsAccelerator/sample_repo#assumptions-and-caveats)

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

- Assumption 1 (ex: missing country records were for customers based in the US, and were re-coded to be US citizens)
    
- Assumption 1 (ex: data for December 2021 was missing - this was imputed using a combination of historical trends and December 2020 data)
    
- Assumption 1 (ex: because 3% of the refund date column contained non-sensical dates, these were excluded from the analysis)



