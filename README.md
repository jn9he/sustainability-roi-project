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
As a data analyst for a sustainability investment firm, I was given the task to analyze historical data related to a large state university's sustainability initative. I analyzed a historical trends within a dataset to provide a data driven approach to justify high impact decisions related the university's sustainability expenditures. Through my analysis of the data, I was able to provide key insights informing investment decisions, identifying inefficiencies in energy management, and quantifying the impact of carbon reduction efforts.

This project consists of four sections:

**Part 1: Trends**
 - Using Excel to take a high-level look at broad operational and environmental trends within the data to identify notable insights for the facilities, finance, and sustainability teams.
Part 2: **Insights**
- With the aid of SQL, extract targeted insights for university decision-makers, such as the performance of solar panel installations, recycling participation rates, and cost-effectiveness of green infrastructure projects
Part 3: **Visualizations**
- Leveraging powerBI create an interactive dashboard for facilities, finance, and sustainability teams (as well as campus leadership) to monitor key performance indicators on an ongoing basis.
Part 4: **Recommendations & Next Steps**
-  Actionable suggestions for future sustainability initiatives, funding allocations, and operational improvements to enhance ROI and environmental impact.

The basic cleaning scripts and inspection of the data [here]()

**Entity Relationship Diagram (ERD):** 

<img width="1267" height="1037" alt="image" src="https://github.com/user-attachments/assets/92d4e59e-51c3-469e-a71a-ba495ea97e62" />

The university has 45 buildings on campus. Data was collected from 2021-2024. Over this period, the campus was subject to 200 sustainability projects.


[](https://github.com/AnalyticsAccelerator/sample_repo#data-structure--initial-checks)


### Executive Summary

Our analysis reveals that investing in **Boiler Replacement** and **Solar Installation** projects offers the highest financial returns and fastest payback periods. We've also identified significant energy inefficiencies stemming from high energy consumption during low-occupancy periods and a strong reliance on HVAC systems to combat temperature extremes. Finally, we've demonstrated the university's progress toward its carbon neutrality goal, with a 14.84% reduction in emissions, primarily driven by offsets and credits. These insights provide a clear strategic direction for allocating future sustainability budgets.

---

### Insights Deep Dive

#### Category 1: Return on Investment (ROI) of Sustainability Projects 💰

Our review of **40 completed projects** reveals a wide range of financial performance across different investment categories. The key to maximizing the firm's impact lies in identifying and prioritizing the most effective project types.

- **Boiler Replacement projects** stand out as the most lucrative, with an impressive average ROI of **13.61%** and the shortest average payback period of **7.35 years**. This makes them a top priority for future investments, as they provide a quick and substantial financial return.
    
- **Solar Installation projects** are the second-best performing category, yielding a strong average ROI of **11.85%** with a payback period of **9.42 years**. These projects not only offer excellent financial performance but also directly support the university's renewable energy goals.
    
- **Water Conservation** projects, while important for resource management, have shown the lowest average ROI (**5.66%**) and the longest payback period (**17.76 years**), suggesting a lower financial priority compared to more impactful projects.
    

---

#### Category 2: Energy Management Inefficiencies & Patterns 💡

A detailed analysis of energy consumption patterns reveals two primary sources of inefficiency that can be targeted for future projects.

- **Weather's Impact on Consumption:** Energy use has a strong relationship with outside temperature, forming a U-shaped curve. As temperatures rise or fall to extremes, energy consumption spikes dramatically. This indicates a high dependence on HVAC systems for heating and cooling, which is a major area for improvement.
    
- **The Occupancy Gap:** A scatter plot of energy consumption versus occupancy levels shows a positive correlation. However, there is a significant baseline energy consumption even when buildings have very few occupants. This indicates that systems like lighting, ventilation, and always-on equipment are not being efficiently managed and offer a great opportunity for savings.
    
- **High-Intensity Buildings:** When analyzing energy intensity (kWh per square foot) by building type, **Dining** and **Athletic** facilities emerge as the most energy-intensive. These buildings should be prioritized for comprehensive energy audits and targeted efficiency projects, as they offer the largest potential for savings.
    

---

#### Category 3: Carbon Emission Impacts & Progress Towards Neutrality 🌱

The university has made measurable progress toward its carbon-neutral goal, primarily by leveraging carbon credits and offsets.

- **Overall Trend:** The analysis of monthly emissions shows a consistent trend of gross emissions, with some seasonal fluctuations. However, the `NetEmissions` line consistently remains below the `TotalEmissions` line, a direct result of the university's strategic use of offsets.
    
- **Emission Hotspots:** When broken down by campus area, **East Campus** stands out as the largest contributor to total emissions, making it a critical focus area for future mitigation efforts. Targeting high-emitting buildings within this cluster could accelerate progress towards carbon neutrality.
    
- **The Role of Offsets:** Over the four-year period, the university's carbon offsets and credits have resulted in a reduction of **3,595 tons of CO2**, or **14.84%** of total gross emissions. While this strategy is effective, it is a financial investment rather than a physical reduction in on-site energy use, highlighting the need for a balanced approach.
    

---

### Recommendations

Based on the insights and findings above, we would recommend the university's **Sustainability & Finance Committee** to consider the following:

- **Prioritize Boiler Replacement and Solar Installation Projects:** These projects have demonstrated the highest ROI and shortest payback periods. Allocating a significant portion of the budget to these categories will ensure a strong financial return while making a considerable environmental impact.
    
- **Conduct Energy Audits on Dining and Athletic Buildings:** As the most energy-intensive facilities on campus, these buildings represent the best starting point for high-impact, targeted energy efficiency upgrades.
    
- **Invest in Building Automation and Controls:** The existence of a strong energy baseline at low occupancy levels suggests a lack of intelligent building management systems. Investing in smart controls, sensors, and scheduling systems can significantly reduce energy waste during off-hours.
    
- **Implement a Targeted Retrofit Strategy:** Focus on projects that specifically address the high energy consumption during temperature extremes. This could include insulation improvements, window replacements, or smart thermostat systems to optimize HVAC performance.
    
- **Explore On-Site Carbon Reduction:** While offsets are effective, they don't solve the root problem. Encourage investments in projects like solar panel installations or direct carbon capture technology to physically reduce the university's carbon footprint and strengthen its long-term neutrality goals.
    

---

### Assumptions and Caveats

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

- **Data Integrity:** It was assumed that the provided data (e.g., `ActualAnnualSavings`, `ROI_Percent`) for completed projects is accurate and reflects true performance.
    
- **Data Completeness:** The analysis of completed projects relies on a limited sample of 40 records. A larger dataset of completed projects would provide more statistically significant insights.
    
- **External Factors:** The analysis does not account for external factors that could influence consumption patterns, such as major events, equipment failures, or changes in utility rates.
    
- **Seasonal Effects:** While temperature correlation was noted, a deeper, more granular analysis would be needed to fully disentangle seasonal effects from other variables impacting energy usage.
    
- **Data Gaps:** Missing values in certain columns (e.g., `Steam_BTU` in `energyConsumption_cleaned`) were handled by excluding the records from the analysis where those specific values were needed, which may slightly alter the calculated averages.



