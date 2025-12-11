# Road-Accidents-Kenya-2016-Analysis
This is a comprehensive data analysis on road acccidents in Kenya from a Kaggle Dataset with insights being drawn from key visualizations and correlation analysis.
## Road Accidents Analysis – Kenya  
[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)  
![Pandas](https://img.shields.io/badge/Library-Pandas-yellow.svg)  
![Seaborn](https://img.shields.io/badge/Library-Seaborn-teal.svg)  
![Folium](https://img.shields.io/badge/Library-Folium-green.svg)  
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)  

---

## **Overview**
This repository contains a comprehensive end-to-end analysis of road traffic accidents in Kenya.  
The goal is to extract insights, identify high-risk locations, analyze temporal patterns, and examine behavioral, environmental, and demographic drivers of road accidents.

The project includes data cleaning, exploratory analysis, temporal trends, geospatial mapping, summary insights, and recommendations.

---
## 1. Project Summary

Road accidents in Kenya continue to impose a significant human and economic burden, despite ongoing mitigation efforts. This project analyzes 1,118 accident records from a compiled 2016–2017 dataset to:

1. Clean and harmonize manually-recorded accident data

2. Identify high-risk counties and hotspots

3. Examine accident patterns across time, roads, vehicle types, victim demographics, and cause codes

4. Extract meaning from unstructured accident narratives

5. Visualize findings through charts and a folium-based choropleth map

6. Establish a foundation for future predictive models or dashboards

Source reference: Kaggle’s accidents_kenya dataset, curated by Waweru Fidelis 

---

## 2. Dataset Description

The dataset includes 15 raw attributes, later renamed, cleaned, and standardized. Key fields include:

- Time and Date of the accident

- County, Road, and Place

- Vehicles involved

- Accident narrative (“Brief Accident Details”)

- Victim demographics (Gender, Age, Victim Type)

- Cause Code mapped to Cause Description and Category

- Number of victims

An additional dataset containing Cause Codes → Descriptions → Categories is merged during preprocessing to enrich the analysis. 


## 3. Key Objectives

1. Clean and standardize a highly irregular, manually recorded dataset

2. Analyze temporal accident patterns (hourly, daily, monthly)

3. Identify high-risk counties and recurrent hotspots

4. Determine dominant causes, categories, and behavioral drivers

5. Examine demographic patterns (gender, age)

6. Visualize accident distribution with bar plots, line plots, and a folium choropleth

7. Summarize key insights and generate actionable recommendations


## 4. Data Cleaning & Preparation

The dataset required extensive correction due to inconsistent formatting, missing entries, mixed data types, and duplicated records. Major steps include:

### 4.1 Column Standardization

Dropped non-informative columns (e.g., Unnamed: 14)

Renamed fields for consistency (e.g., TIME 24 HOURS → time; NO. → number_of_victims) 

Applied uniform case formatting and spacing corrections

### 4.2 Date & Time Parsing

Reconstructed missing year information

Normalized time using zero-padding and conversion into proper time objects

Converted dates into pandas datetime format

### 4.3 Handling Duplicates & Missing Values

Identified and removed exact and near-duplicate accident records

Retained rows with missing Age values to preserve essential accident-level information

### 4.4 Categorical Cleaning

County name harmonization (e.g., HOMABAY → HOMA BAY, KERCHO → KERICHO)

Standardized gender values (e.g., “2M & 3F” → “BOTH”; “J” → “UNKNOWN”)

Merged detailed cause codes dataset into the main dataset

### 4.5 Type Casting

Converted:

- AGE → numeric

- CAUSE CODE → integer

- NUMBER OF VICTIMS → integer


## 5. Exploratory Data Analysis

### 5.1 Descriptive Statistics

Average victim age: 34 years (range 1.5–90; many missing values)

Average victims per accident: ~1.18

Dataset skewed toward single-victim records

### 5.2 Temporal Analysis

Data spans Jan 2016 – Dec 2017, but 2017 entries are markedly underrepresented

Peak accident months: April, June, July

Peak accident hours: 17:00–20:00

Seasonal trend: mid-year spike, year-end dip

### 5.3 Geographic Analysis

Top counties by accidents:

- Nairobi (183)

- Kiambu (98)

- Nakuru (77)

- High-risk hotspot examples: Kangemi, Shell Petrol Station, State House area

### 5.4 Cause Codes & Categories

Most common Cause Description:

- Cause not traced (218)

- Losing control (159)

- Improper overtaking (109)

- Speeding (78)

Most common Categories:

- Driver-related (512)

- Other Cause (219)

- Pedestrian (163)

### 5.5 Gender Analysis

Male victims: 83.9%

Female victims: 12.9%

Indicates strong male overrepresentation in crash involvement


### 5.6 Folium Choropleth Map

A county-level heatmap visualizes spatial variation in accident concentration across Kenya.
Output: accidents_choropleth.html


## 6. Visualizations Included

The notebook generates multiple figures, including:

- Histograms of numeric variables

- Countplots for counties, categories, and gender distribution

- Monthly and hourly time-series plots

- Gender vs category and gender vs description comparisons

- County vs accident category charts (stacked and grouped bars)

- Choropleth maps using GeoJSON and folium

All figures are intended for export into dashboards or presentations.


## 7. Key Findings
Accident Drivers:

- Majority caused by driver behavior (speeding, overtaking, losing control)

- High incidence of accidents labelled “cause not traced,” indicating reporting gaps

High-Risk Locations:

- Nairobi, Kiambu, and Nakuru counties record the highest frequency of accidents

- Specific recurring hotspots near petrol stations, markets, and busy urban corridors

Temporal Patterns:

- Evening hours (17:00–20:00) are the most dangerous

- Mid-year period shows a noticeable spike in total accidents

Victim Demographics

Strong male dominance in victim records

Age distribution centered around early to mid-30s


## 8. Recommendations

Based on identified patterns:

1. Targeted enforcement in Nairobi Metropolitan counties and top hotspots

2. Driver-focused campaigns addressing speeding, overtaking, and lane discipline

3. Improved signage, lighting, and pedestrian safety near high-risk urban nodes

4. Strengthening accident reporting systems to reduce “cause not traced” entries

5. Deploying predictive modelling to proactively identify where/when crashes may occur


## **Project Features**
- Cleaning and standardization of messy accident data  
- Cause-code enrichment with category mapping  
- Exploratory Data Analysis (EDA)  
- Temporal trend analysis (hourly, monthly, yearly)  
- County-level accident analysis  
- Folium choropleth heatmap  
- Gender and demographic breakdown  
- Accident cause hierarchy exploration  
- Export-ready visuals for reporting  
- PowerPoint-ready summarized insights  

---

## **Repository Structure**
project/
│
├── data/
│ ├── accidents-database.csv
│ ├── cause_codes.csv
│ └── kenyan_counties.geojson
│
├── notebooks/
│ └── Roadaccidentsanalysis.ipynb
│
├── outputs/
│ ├── accidents_choropleth.html
│ ├── figures/
│ └── processed/
│
├── README.md
└── LICENSE
