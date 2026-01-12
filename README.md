# Airline Data Analysis (pandas)

## Introduction

This project applies Python’s Pandas, NumPy, Matplotlib, and Seaborn libraries to conduct in-depth data analysis on 
a simulated airline database documented [here](https://github.com/data-analysis-colab/database_creation_airline_python/blob/master/README.md).
The analysis focuses on topics that receive limited attention in the corresponding [SQL-based project](https://github.com/data-analysis-colab/analysis_synth_airline_data_sql/blob/master/README.md), including 
cohort analysis, passenger class profitability, aircraft utilization, and customer behavior.

An [accompanying Jupyter Notebook](analysis_pandas.ipynb) contains the full analysis.

A global locale and language setting allows data formats and visualizations to appear in either English or German, 
supporting region-specific formatting for decimals, separators, and annotations.

## Problem Statement

Airlines operate complex systems where profitability, customer retention, and operational efficiency are interconnected.
The goal of this analysis is to explore key business questions that inform strategic decision-making:

- How do customer cohorts behave over time in terms of retention and lifetime value (LTV)?
- What is the financial performance of flights across different passenger classes?
- How efficiently and reliably are various aircraft models utilized?
- How do demographic attributes (age, gender, nationality) influence customer booking behavior?

## Skills Demonstrated

- **Data Wrangling**  
Cleaning, merging, and transforming relational data in Pandas.
- **Cohort and Retention Analysis**  
Identifying customer retention trends and lifetime value.
- **Financial Modelling**  
Evaluating profitability at the flight and passenger-class level.
- **Operational Analytics**  
Assessing aircraft utilization, reliability, and performance stability.
- **Collaborative Analysis Workflow**  
Co-developing notebooks, aligning analytical steps, cross-checking transformations, and ensuring results remain 
consistent with SQL-based counterparts.
- **Visualization**  
Creating clear and insightful visualizations with Matplotlib and Seaborn.
- **Dual-Language Setup**  
Enabling user choice between English vs. German labeling and annotation.

## Data Sourcing

The data originates from a Simulated Airline Database, mimicking real-world airline operations, including entities
such as:

- **Flights**: Scheduling, distance, duration, and operational performance.
- **Bookings**: Passenger-class distribution, pricing, and lead times.
- **Customers**: Demographics, frequent flyer status, and check-in behavior.
- **Aircraft**: Manufacturer, capacity, range, and reliability metrics.

The synthetic nature of the dataset allows controlled experimentation and reproducibility while maintaining 
realistic interdependencies between operational and commercial dimensions.

## Localization and Display Formatting

A modular localization setup provides bilingual output:

- **English (default)**
- **German (optional)**

The function `set_display_locale(lang)` switches locale-dependent number and text formatting globally within the Pandas 
display environment. Depending on the selected language:

- Decimal separators (`.` vs. `,`) and thousand grouping rules adapt.
- Plot labels, axis titles, and footnotes are automatically translated.
- Visualization output file paths are routed to language-specific directories 
  ([visualizations_eng/](visualizations_eng) vs. [visualizations_ger/](visualizations_ger)).

This enables consistent localization for both numeric and textual elements of each figure.

## Modelling, Analysis, and Visualisation

All visualizations are generated using Matplotlib and Seaborn. ChatGPT assisted in customizing annotations.

### Cohort Analysis

- Customer cohorts are grouped quarterly (due to the three-year data window).
- For each cohort:
  - Average retention time (quarters) and lifetime value (LTV) are calculated.
  - A retention matrix shows cohort survival across multiple quarters.
- Visualizations:
    - [Retention Time & LTV by Cohort](visualizations_eng/(01)_cohorts_retention_ltv.png)
    - [Customer Retention Rates by Quarterly Cohorts](visualizations_eng/(02)_cohort_retention_rates.png)

> *Note*: The uniform retention pattern (21–23%) reflects simulation constraints rather than real-world dynamics.

### Passenger Class Profitability

- For each flight and class:
  - Revenue, cost, profit, and profit margin (%) are computed.
  - Flights are categorized into six performance tiers by profit margin.
  - Average profit and flight share per tier are displayed in a heatmap.
- Visualization:
  - [Average Profit and Total Bookings Share by Passenger Class and Profit Margin Tier](visualizations_eng/(03)_class_profits.png)

>**Insights**:
> - First class consistently yields top-tier profit margins.
> - Economy class shows broader variation, including loss-making flights.
> - Business class maintains moderate, stable profitability.

### Aircraft Utilization & Performance

- Metrics collected per flight include utilization frequency, profitability, and delay data.
- Grouped by manufacturer, model, capacity, and range:
  - Utilization & Deployment: Intensity of aircraft use relative to range and capacity.
  - Commercial Performance: Impact of booked rate on profitability.
  - Profitability Stability: Average profit vs. standard deviation (stability ratio).
  - Operational Reliability: Mean departure and arrival delays.
- Visualization:
  - [Aircraft Utilization by Flight Distance, Manufacturer, and Seat Capacity](visualizations_eng/(04)_aircraft_util.png)
  - [Profitability vs Booked Rate by Aircraft Manufacturer](visualizations_eng/(05)_aircraft_commercial.png)
  - [Profit Stability by Aircraft Model and Manufacturer](visualizations_eng/(06)_aircraft_profit_stability.png)
  - [Average Delay Times by Aircraft Model](visualizations_eng/(07)_aircraft_reliability.png)

>**Key Findings**:
> - Airbus and Boeing long-range aircraft exhibit the most intensive use and highest profit stability but also longer delays.

### Customer Behavior

- Customers are categorized by age group (age based on their most recent flight).
- Each booking is encoded for:
  - Passenger class
  - Frequent flyer status
  - Lead time window
  - Time of day of booking
- Data is grouped by age group, gender, and nationality to measure:
  - Booking frequency, check-ins, and class preferences.
  - Distribution of frequent flyer tiers and booking behaviors.
- Visualization:
  - [Customer Shares (%) by Gender and Age Group](visualizations_eng/(08)_customer_age_gender.png)
  - [Customer Shares by Nationality (Top 10)](visualizations_eng/(09)_customer_nationality.png)
  - [Average Booking Class Mix by Age Group (%)](visualizations_eng/(10)_bookings_class.png)
  - [Missed Check-In Rate by Gender and Age Group](visualizations_eng/(11)_missed_check_ins.png)
  - [Booking Lead Time Distribution by Gender](visualizations_eng/(12)_lead_times_gender.png)
  - [Booking Lead Time Distribution by Age Group](visualizations_eng/(13)_lead_times_age.png)
  - [Frequent Flyer Status Distribution by Gender](visualizations_eng/(14)_flyer_status_gender.png)
  - [Frequent Flyer Status Distribution by Age Groups](visualizations_eng/(15)_flyer_status_age.png)
  - [Booking Time Distribution by Nationality (Top 10)](visualizations_eng/(16)_booking_times.png)

> **Key Findings**:
> - Older travelers favor premium classes and longer lead times.
> - Younger passengers have higher missed check-in rates.
> - Men are slightly more represented in higher loyalty tiers.
> - Nationality correlates with preferred booking times.

## Conclusion

This project demonstrates how simulated airline data can be leveraged for realistic, multidimensional analysis.
By integrating financial, operational, and customer perspectives, it provides insights into:

- The stability of airline profits across different service tiers
- How aircraft utilization affects both performance and reliability
- Patterns in customer retention and loyalty
- Behavioral trends across demographics and booking habits

Although based on simulated data, the framework is transferable to real-world airline datasets for strategic and 
operational decision support.

## Authors
Jan H. Schüttler ([LinkedIn](https://www.linkedin.com/in/jan-heinrich-sch%C3%BCttler-64b872396/)), Behzad Nematipour ([LinkedIn](https://linkedin.com/in/behzad-nematipour-99b8b4399))
