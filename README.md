# NYC Airbnb Market Structure & Pricing Analysis

## Project Overview

This project analyzes Airbnb listings in New York City to understand market structure and identify key drivers of listing price. Using structured data cleaning, feature engineering, exploratory data analysis (EDA), and explanatory visualization techniques, this analysis investigates how property characteristics, location, and host status influence pricing behavior.

The project is divided into two components:

- **Exploratory Analysis Report** – Focused on data cleaning, distribution analysis, and relationship exploration.
- **Explanatory Analysis Report** – Focused on communicating key insights and pricing drivers through structured storytelling and visualization.

---

## Objectives

- Clean and structure raw Airbnb listing data  
- Investigate pricing distribution and outliers  
- Identify relationships between property characteristics and price  
- Evaluate the impact of borough (location) on listing price  
- Assess whether Superhost status influences pricing  
- Present findings in both exploratory and explanatory formats  

---

## Dataset

- **Source:** Inside Airbnb (NYC Listings Dataset)  
- **Observations (after cleaning):** ~22,000 listings  

### Features Used
- `price`
- `room_type`
- `neighbourhood_group_cleansed`
- `bedrooms`
- `bathrooms`
- `beds`
- `availability_365`
- `calculated_host_listings_count`
- `host_is_superhost`
- `accommodates`

---

## Data Cleaning & Feature Engineering

Key preprocessing steps included:

- Removed listings with zero availability to focus on active inventory  
- Dropped missing `price` values  
- Median imputation (grouped by room type) for:
  - Bedrooms
  - Bathrooms
  - Beds  
- Converted price from string format to numeric  
- Created a `log_price` variable to handle heavy right skew  
- Applied a 99th percentile price cap for filtered price analysis  

Log transformation was used due to significant right skew (mean = $212 vs median = $140), indicating extreme high-price listings distort average metrics.

---

## Key Findings

### 1. Price Distribution
- Listing prices are heavily right-skewed.
- A small number of extreme listings significantly inflate the mean.
- Log transformation reveals a more normalized distribution suitable for modeling.

### 2. Property Size & Price
- Bedrooms, bathrooms, and bed count show moderate positive relationships with price.
- Price increases appear to taper at higher property sizes.
- Most listings cluster in 1-bedroom configurations.

### 3. Location Premium
- Manhattan listings consistently occupy higher price bands compared to other boroughs.
- Location exerts a strong influence across all room types.

### 4️. Room Type Impact
- Hotel rooms command the highest median prices.
- Entire home/apt listings slightly outnumber private rooms.
- Smaller unit types dominate overall inventory.

### 5️. Superhost Status
- Superhost status does not show a strong pricing premium.
- Price distributions for superhosts and non-superhosts are similar.
- This suggests reputation may influence occupancy rather than price.

---

## Market Insights

- NYC Airbnb inventory is concentrated in smaller units.
- Entire home listings slightly outnumber private rooms, suggesting some degree of commercial-scale hosting.
- Availability patterns indicate many hosts operate year-round rather than seasonally.
- Location and property type influence price more strongly than host designation.

---

## Limitations

- No amenity-level data included  
- No occupancy rate or revenue data  
- No review score integration  
- Seasonal effects not analyzed  
- Analysis is cross-sectional (snapshot in time)  

---

## Future Work

- Build a regression model to quantify price drivers  
- Introduce occupancy proxy using availability trends  
- Segment hosts by listing volume  
- Apply clustering to identify market segments  
- Conduct time-series analysis on price variation  

---

## Tools & Technologies

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Jupyter Notebook  

---

## Project Structure

```
├── exploratory_report.ipynb
├── explanatory_report.ipynb
├── exploratory_report.html
├── explanatory_report.html
├── data/
│ ├── raw/
│ └── clean/
└── README.md
```

---

## What This Project Demonstrates

- End-to-end data cleaning workflow  
- Structured exploratory data analysis  
- Outlier handling and log transformation  
- Multivariate visualization techniques  
- Statistical reasoning in interpretation  
- Clear separation between exploratory and explanatory analysis  
