# Home Sales Analysis Using PySpark SQL

## Objective
This assignment aims to analyze home sales data using **PySpark SQL** to extract insights related to house prices based on different attributes. The dataset is sourced from an **AWS S3 bucket**, and the analysis includes SQL queries, caching techniques, and partitioning for optimized performance.

---

## Steps Performed

### 1. File Management & Setup
- Renamed the `Home_Sales_starter_code.ipynb` file as `Home_Sales.ipynb`.
- Imported necessary **PySpark SQL functions** for data processing.
- Initialized PySpark and created a Spark session.

### 2. Data Ingestion
- Loaded `home_sales_revised.csv` from the **AWS S3 bucket** into a **PySpark DataFrame**.
- Created a **temporary table** called `home_sales` for SQL-based analysis.

### 3. SQL Queries to Answer Key Questions

#### 1. Average price for four-bedroom houses sold each year
   - Used **YEAR(DATE)** to group sales by year and calculated the **rounded average price**.

#### 2. Average price of homes built per year with 3 bedrooms and 3 bathrooms
   - Filtered houses based on **bedrooms and bathrooms** and computed the **average price**.

#### 3. Average price of homes built per year with specific conditions
   - Criteria: **3 bedrooms, 3 bathrooms, 2 floors, and a minimum of 2,000 sqft**.
   - Grouped by `date_built` and calculated the **average price**.

#### 4. Average price per "view" rating for homes with prices >= $350,000
   - Filtered properties with **average price >= $350K** and computed results.
   - Measured query runtime for performance comparison.

### 4. Caching & Performance Optimization
- **Cached** the `home_sales` temporary table.
- Verified the cache status using PySpark.
- Reran the **"view rating" query** using cached data and compared runtime to the uncached version.

### 5. Partitioning & Parquet Optimization
- Partitioned the dataset by **`date_built`** and saved it in **Parquet format**.
- Created a temporary table for the partitioned data.
- Re-executed the **"view rating" query** to compare performance improvements.

### 6. Cleanup & Submission
- **Uncached** the `home_sales` temporary table and verified its uncached status.
- Downloaded `Home_Sales.ipynb` and uploaded it to the **Home_Sales GitHub repository**.

---

## Conclusion
This analysis efficiently processed large-scale home sales data using **PySpark SQL**, showcasing:
- **SQL-based querying for structured insights**.
- **Performance enhancements via caching and partitioning**.
- **Optimized data storage using Parquet format**.

The findings provide valuable insights into **home pricing trends, property characteristics, and data processing efficiencies** in big data environments.
