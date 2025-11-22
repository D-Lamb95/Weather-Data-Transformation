# Weather Data Transformation and Cleaning

## Overview  
This project focuses on transforming, cleaning, and standardizing raw weather data collected from multiple sources. The goal is to prepare a unified dataset suitable for analysis, visualization, and machine learning workflows. The work includes fixing inconsistent formats, parsing dates, converting temperature units, handling missing values, and engineering new features.

---

## Data Description  
The dataset includes the following weather-related variables:

- **Date** – daily timestamp  
- **tavg** – average temperature  
- **tmin** – minimum temperature  
- **tmax** – maximum temperature  
- **Wind speed**  
- **Humidity**  
- **Precipitation**  
- Additional variables depending on source (e.g., evapotranspiration, radiation)

Different files contained inconsistent structures, mixed data types, and missing values, requiring comprehensive preprocessing.

---

## Methods  

### 1. Data Cleaning  
- Standardized column names and removed inconsistencies  
- Parsed date strings into proper datetime format  
- Extracted year, month, and day components  
- Removed or corrected invalid values  
- Converted numeric strings into proper numeric types  

### 2. Temperature Conversion  
Temperature fields provided in Celsius were converted into Fahrenheit using:

```
F = (C * 9/5) + 32
```

The transformation ensured consistent units across all datasets.

### 3. Handling Missing Values  
- Filled numeric missing values using median imputation  
- Checked for outliers or impossible values (e.g., negative precipitation)  
- Removed rows with severe data quality issues  

### 4. Feature Engineering  
New fields were created to support analyses:

- **Temperature range:** `tmax - tmin`  
- **Rolling temperature averages** (7-day or 30-day windows)  
- Optional seasonal indicators (month, quarter)

### 5. Exporting Clean Data  
The cleaned and transformed dataset was exported as a structured CSV file suitable for:

- Visualization tools  
- Forecasting models  
- SQL/Hive pipelines  
- Machine learning workflows  

---

## Key Insights  

- Weather datasets often require extensive preprocessing before downstream analysis is possible.  
- Many variables showed inconsistent formatting and required type corrections.  
- Properly formatted weather datasets improve later steps such as correlation analysis, forecasting, and environmental modeling.  
- Converting temperatures and standardizing units was essential for combined datasets.  

---

## Requirements  

Install required Python packages:

```bash
pip install pandas numpy matplotlib
```

---

## How to Use  

1. Open the Jupyter notebook included in this repository.  
2. Load the raw weather dataset(s).  
3. Run all preprocessing steps to standardize the data.  
4. Export the clean dataset for further analysis or modeling.  

---

## Future Improvements  

- Automate scraping and API calls to create a live weather ingestion pipeline  
- Add integration with OpenWeatherMap or CIMIS APIs  
- Build forecasting models using ARIMA or machine learning  
- Create dashboards to explore weather trends over time  

---

## Files Included  

- `Weather_Data_Transformation.ipynb` – full cleaning and transformation workflow  
- Raw dataset(s) in CSV format  
- Cleaned dataset output  
- `README.md` – project documentation  

