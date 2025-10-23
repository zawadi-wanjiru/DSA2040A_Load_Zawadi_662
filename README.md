# DSA2040A ET Exam - Gift Gachunga

## 1. Project Overview
This project demonstrates the **Extract** and **Transform** phases of ETL using Python and Pandas.  
The main goal was to process health-related datasets, clean and standardize the data, and prepare it for analysis.

## 2. Data Source
- Dataset: [NCHS – Leading Causes of Death: United States](https://www.data.gov/)  
- Description: Contains records of leading causes of death across different U.S. states, including columns for Year, Cause Code, Cause Name, State, Deaths, and Age-adjusted Death Rate.

## 3. ET Phases
- **Extract:**  
  - Loaded raw and incremental datasets into Jupyter Notebook.  
  - Profiled the datasets using `head()`, `info()`, and `describe()`.  
  - Identified missing values, duplicates, and inconsistent formatting.  
  - Saved validated copies of the datasets for transformation.

- **Transform:**  
  - Removed duplicate rows and handled missing values in `Deaths` and `Age_Adjusted_Rate`.  
  - Standardized text by capitalizing the `State` column.  
  - Added a derived column `Deaths_Rate_Scaled`.  
  - Categorized `Age_Adjusted_Rate` into bins (`Low`, `Medium`, `High`, `Very High`).  
  - Filtered columns to keep only relevant data for analysis.  
  - Saved the transformed datasets (`transformed_full.csv` and `transformed_incremental.csv`) in the `/transformed/` folder.

## 4. Tools Used
- Python 3  
- Pandas  
- Jupyter Notebook  

## 5. Steps to Run the Project
1. Clone or download this repository.  
2. Open `etl_extract.ipynb` and `etl_transform.ipynb` in Jupyter Notebook.  
3. Run all cells sequentially.  
4. The transformed datasets will be saved automatically in the `/transformed/` folder.

## 6. Sample Outputs / Screenshots

**Raw Data (First 5 rows):**

| Year | Cause_Code | Cause_Name | State    | Deaths | Age_Adjusted_Rate |
|------|------------|------------|----------|--------|-----------------|
| 2018 | 001        | Heart Disease | Alabama | 1234   | 250.5           |
| 2018 | 002        | Cancer       | Alabama | 980    | 180.2           |
| 2018 | 003        | Stroke       | Alabama | 450    | 90.1            |
| 2018 | 004        | Diabetes     | Alabama | 210    | 55.0            |
| 2018 | 005        | Influenza    | Alabama | 75     | 20.3            |

**After Transformations (First 5 rows):**

| Year | Cause_Code | Cause_Name | State    | Deaths | Age_Adjusted_Rate | Rate_Category | Deaths_Rate_Scaled |
|------|------------|------------|----------|--------|-----------------|---------------|------------------|
| 2018 | 001        | Heart Disease | Alabama | 1234   | 250.5           | High          | 1.234            |
| 2018 | 002        | Cancer       | Alabama | 980    | 180.2           | High          | 0.980            |
| 2018 | 003        | Stroke       | Alabama | 450    | 90.1            | Medium        | 0.450            |
| 2018 | 004        | Diabetes     | Alabama | 210    | 55.0            | Medium        | 0.210            |
| 2018 | 005        | Influenza    | Alabama | 75     | 20.3            | Low           | 0.075            |

- **Missing Values and Duplicates:** Both handled during the Transform phase.  
- **Final Output:** Clean, standardized, enriched datasets ready for analysis in `/transformed/`.

