# YEDS Capstone Project
**Topic: Trends in U.S. Cities Hazard Identification and Climate Initiatives in CDP Reporting (2019-2023)**

Anna Brause, March 2026
# Project Rationale
As climate change accelerates, cities are on the frontlines of managing environmental hazards as they are home to 55% of the world's population, a figure that is projected to reach 68% by 2050 (United Nations, 2018). Municipal governments are tasked with identifying hazards, assessing vulnerability, and implementing adaptation programs, all while navigating competing budget pressures, shifting federal priorities, and unexpected disruptions like the COVID-19 pandemic. Understanding how cities are actually performing on climate change related issues and identifying any trends associated with hazard identification and climate adaptation planning over time is critical for informing more effective urban climate policy and protecting the large populations who call these cities home. 

This project analyzes five years of Carbon Disclosure Project (CDP) Cities Survey data from 18 of the most populous U.S. cities to examine how climate risk assessments, hazard identification, and adaptation program implementation has evolved from 2019 to 2023. The CDP Cities Survey is one of the most comprehensive standardized frameworks through which cities voluntarily disclose their climate risks and actions, making it a valuable tool for tracking municipal climate progress over time.
# Project Questions
1. How have urban climate risk assessments, hazard reporting, and adaptation programs changed across major U.S. cities from 2019 to 2023?
2. Did the COVID-19 pandemic measurably affect municipal climate risk reporting and adaptation efforts?
3. How do city size, population density, and primary hazard type influence the implementation of climate risk assessments and adaptation programs?
# Data Sources
**Dataset:** CDP Cities Survey Response Data (2019-2023)

**Source:** Carbon Disclosure Project (CDP) Open Data Portal

**Coverage:** 18 most populous U.S. cities, 5 annual reporting cycles (Note: the original dataset includes hundreds of major global cities, and my analysis began with 20 U.S. cities, but two removed during the initial cleaning process due to insufficient response data across the reporting period.)

**Unit of Analysis:** City-year (90 observations total). Each row in the dataset represents one city in one reporting year. (18 cities observed across 5 years produces 90 total records.)

**Key Variables:** Climate risk assessment completion status, number of hazards identified, most common hazard type, number of adaptation programs, city population (2023), land area (2023), and population density (2023).

Note on population and land area: Raw CDP survey data contained missing population and land area values for most cities in 2019-2022, as cities reported inconsistently across years. To address this, 2023 values - the most recent and complete year available - were extracted and applied uniformly across all reporting years via a left join on city name. Population density was then recalculated as population divided by land area (residents per sq km). This standardization is appropriate because population and land area are relatively stable city-level characteristics across the five-year window examined, and using a single reference year avoids introducing inconsistencies from patchwork data across multiple sources.
# Analytical Goals
- Track trends in climate risk assessment completion and hazard identification across cities from 2019-2023

- Examine how adaptation program implementation has changed over time and whether it responds to hazard identification

- Explore whether the COVID-19 pandemic influenced climate reporting and adaptation metrics

- Analyze how city size, population density, and hazard type relate to adaptation program implementation

- Apply statistical methods including correlation, linear regression, and ANOVA to test relationships between key variables
# Table of Contents
**1. Data Loading & Inspection**

**2. Data Cleaning & Standardization**

**3. Exploratory Data Analysis (EDA)**

**4. Trend Analysis: Climate Risk Assessments & Hazard Identification**

    4.1 CDP Participation Over Time
    
    4.2 Average Hazards Identified Per Year

    4.3 Per-City Hazard Trends (Top 6 Cities)

    4.4 Most Common Hazard Types

    4.5 Hazard Type Frequency Heatmap

**5. Trend Analysis: Adaptation Programs**

**6. City Size & Density Analysis**

    6.1 Population Density vs. Hazards

    6.2 City Population vs. Adaptation Programs

    6.3 Population Density vs. Adaptation Programs

    6.4 Correlation Tests

**7. Statistical Analysis: Correlation, Regression & ANOVA**

    7.1 Overall Hazard-Adaptation Correlation

    7.2 Year-by-Year Correlation Trend

    7.3 Multiple Regression: Predictors of Adaptation Programs

    7.4 Time-Trend Regression: Hazard Identification Over Time

    7.5 ANOVA: Adaptation Programs by Hazard Type

**8. COVID-19 Era Analysis**

**9. Summary, Conclusions & Limitations**
# Limitations
- Population, land area, and density were standardized to 2023 values and applied uniformly across all years. This simplification assumes these are stable characteristics, which limits analysis of how city growth may have influenced climate reporting over time.

- The dataset covers only 18 large U.S. cities. Findings are not generalizable to smaller or mid-sized municipalities, or cities outside of the U.S., which may face different resource constraints, political dynamics, and reporting cultures.

- The COVID-19 interpretation is observational. The dataset does not contain budget, staffing, or public health variables that could confirm a causal link between the pandemic and changes in reporting behavior.

- The most_common_hazard variable captures only the single top hazard per city per year, which may underrepresent multi-hazard exposure in complex urban environments.

- CDP reporting is voluntary and self-reported, which may introduce reporting bias — cities with stronger climate programs may be more likely to participate, potentially skewing results toward higher adaptation counts.

- The most recent fully completed CDP Cities dataset is from 2023, leaving a time gap between then and the present day (2026). This analysis therefore does not account for post-2023 developments.
