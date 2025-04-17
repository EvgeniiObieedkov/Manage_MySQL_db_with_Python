### Manage MySQL DB with Python — Data Pipeline Project

#### Project Type  
**Python pipeline** for automated data extraction, transformation, and loading (ETL) into a **MySQL database**.

#### Goal  
To build a reusable script that loads Excel data, processes it, and populates a MySQL database with structured tables for analysis and querying.

#### Process  

1. **Data Extraction**  
   - Loaded three Excel sheets (`orders`, `customers`, `products`) into Pandas DataFrames using `pd.ExcelFile()`.

2. **Data Cleaning & Transformation**  
   - Renamed columns to snake_case for consistency.  
   - Trimmed unnecessary or empty fields (e.g., cleaned `orders` DataFrame to only include valid columns).  
   - Replaced code values with human-readable names using dictionaries (e.g., `"Ara"` → `"Arabica"`).  

3. **MySQL Setup**  
   - Connected to MySQL via `mysql.connector` and `SQLAlchemy`.  
   - Created a database (`coffee_db`) and replaced existing tables if needed.

4. **Data Loading**  
   - Used `DataFrame.to_sql()` to load processed DataFrames into MySQL tables.

5. **Verification via SQL Queries**  
   - Checked data integrity with test queries:  
     - View sample records.  
     - Identify missing email addresses.  
     - Perform joined queries to get order info by coffee type and date.
