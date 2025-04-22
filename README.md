# Contoso Sales Data Analysis Portfolio

## Project Overview
A comprehensive analysis of the Contoso retail dataset using PostgreSQL and Python, demonstrating advanced SQL analytics and data visualization techniques. This project showcases various analytical methodologies to derive actionable business insights from a complex retail dataset.

## Database Schema
![Contoso Database Schema](Screenshot%202025-04-22%20171824.png)

## Database Details
- **Name**: contoso_100k
- **Type**: PostgreSQL 17.4
- **Tables**: 
  - `sales`: Transaction records including order dates, quantities, prices, and exchange rates
  - `product`: Comprehensive product information and categorization
  - `customer`: Detailed customer demographics and geographical data

## Technical Environment

### Database Connection
The project leverages JupySQL (formerly IPython-SQL) for seamless PostgreSQL integration within Jupyter notebooks:

```python
# Import required libraries
import pandas as pd
from sqlalchemy import create_engine
%load_ext sql

# Database connection
%sql postgresql://postgres:'your_password'@localhost:5432/contoso_100k

# Enable automatic pandas DataFrame conversion
%config SqlMagic.autopandas = True
```

### JupySQL Features Used
- **Magic Commands**: 
  - `%%sql`: For multi-line SQL queries
  - `%sql`: For single-line queries
- **Automatic DataFrame Conversion**: Results automatically convert to pandas DataFrames
- **Named Parameters**: Disabled for better compatibility
- **Direct PostgreSQL Integration**: Native PostgreSQL syntax support

## Analysis Notebooks

### 1. Database Exploration (`01_database-exploration.ipynb`)
- Initial database connection and schema exploration
- Table relationship mapping
- Basic data quality checks

### 2. Time-Based Analysis (`02_change_over_time_analysis.ipynb`)
Examines sales patterns over time to identify growth opportunities and optimize inventory:
- Analyzes daily/monthly/yearly sales trends to forecast demand
- Compares performance across different time periods to measure growth
- Identifies seasonal patterns to optimize stock levels and promotions

SQL Functions Used:
- `DATE_TRUNC()` for time period aggregation
- `EXTRACT()` for date component extraction
- `LAG()` for period-over-period comparisons
- `AVG()`, `SUM()` for aggregations
- `INTERVAL` for date arithmetic

### 3. Cumulative Analysis (`03.cummulative_analysis.ipynb`)
Tracks progressive business performance to understand growth dynamics:
- Monitors running sales totals to assess progress toward targets
- Uses moving averages to smooth volatility and spot underlying trends
- Visualizes growth trajectories to identify acceleration/deceleration periods

SQL Functions Used:
- `SUM() OVER (ORDER BY date)` for running totals
- `AVG() OVER (ROWS BETWEEN)` for moving averages
- `LAG()` for growth rate calculations
- `PARTITION BY` for segmented analysis

### 4. Performance Analysis (`04_Performance_analysis.ipynb`)
Evaluates business effectiveness across key metrics:
- Measures product success through sales, margins, and turnover rates
- Tracks revenue changes to identify growing/declining product lines
- Analyzes sales variations to understand performance volatility

SQL Functions Used:
- `STDDEV()`, `VARIANCE()` for volatility measures
- `PERCENTILE_CONT()` for distribution analysis
- `CASE WHEN` for categorical grouping
- `COUNT()`, `SUM()` for basic metrics

### 5. Segmentation Analysis (`05_Segmentation_Analysis.ipynb`)
Groups products strategically to optimize inventory and pricing:
- Categorizes products by cost to inform pricing strategies
- Analyzes distribution patterns to optimize stock levels
- Groups items by category to identify department performance

SQL Functions Used:
- `NTILE()` for segmentation
- `WIDTH_BUCKET()` for range grouping
- `GROUP BY` with `HAVING` for filtered aggregations
- `PERCENT_RANK()` for relative positioning

### 6. Part-to-Whole Analysis (`06_Part_to_whole_Analysis.ipynb`)
Examines relative contributions to understand business composition:
- Maps category revenue distribution to focus resources
- Tracks market share evolution to assess competitive position
- Analyzes cost structures to optimize pricing strategies

SQL Functions Used:
- `RATIO_TO_REPORT()` for share calculations
- `SUM() OVER()` for total calculations
- `ROUND()` for percentage formatting
- `DECIMAL` casting for precise calculations

### 7. Rank Analysis (`07_Rank_analysis.ipynb`)
Identifies top performers to guide strategic decisions:
- Highlights best-selling products to optimize inventory
- Ranks customers by value to guide relationship management
- Creates revenue hierarchies to focus sales efforts

SQL Functions Used:
- `RANK()`, `DENSE_RANK()` for ordering
- `ROW_NUMBER()` for unique ordering
- `FIRST_VALUE()`, `LAST_VALUE()` for boundary analysis
- `ORDER BY` with multiple criteria

### 8. Cohort Analysis (`08_Cohort_analysis.ipynb`)
Studies customer groups to improve retention strategies:
- Tracks customer groups over time to measure loyalty
- Analyzes retention patterns to reduce churn
- Maps purchase behaviors to predict future activity

SQL Functions Used:
- `FIRST_VALUE()` for cohort assignment
- `DATEDIFF()` for time between events
- `WITH` for complex CTEs
- `CROSS JOIN` for cohort matrices

### 9. Customer Analysis (`09_Customer_report.ipynb`)
Develops deep customer understanding to enhance relationships:
- Creates detailed customer profiles for targeted marketing
- Identifies buying patterns to personalize offerings
- Segments customers by value to optimize service levels

SQL Functions Used:
- `STRING_AGG()` for profile concatenation
- `COUNT(DISTINCT)` for unique counts
- `PERCENTILE_DISC()` for value segmentation
- `COALESCE()` for handling nulls
## Key Reports

### Product Report (`product_report.ipynb`)
- Comprehensive product metrics
- Performance segmentation
- KPI tracking including:
  - Total orders
  - Sales metrics
  - Customer reach
  - Product lifecycle

### Customer Report (`Customer_report.ipynb`)
- Customer behavior analysis
- Purchase patterns
- Value segmentation

## Technical Stack
- PostgreSQL
- Python
- Libraries:
  - JupySQL (SQL magic commands)
  - Pandas
  - SQLAlchemy
  - Plotly Express
  - IPython SQL Magic

## SQL Techniques Demonstrated
- Complex JOIN operations
- Window functions (RANK, ROW_NUMBER, LAG/LEAD)
- Common Table Expressions (CTEs)
- Aggregate functions
- Date/Time manipulations
- Subqueries and derived tables
- CASE statements
- String operations
- Data type conversions

## Key Insights
- Product performance categorization (High, Mid, Low performers)
- Customer segmentation based on purchase behavior
- Sales distribution across product categories
- Temporal trends in revenue
- Cost-based product segmentation

## Visualization Techniques
- Interactive charts using Plotly
- Time series analysis
- Distribution plots
- Segmentation visualizations
- Cohort matrices

## Skills Demonstrated
- SQL querying
- Data analysis
- Business intelligence
- Data visualization
- Statistical analysis
- Window functions
- Cohort analysis
- Segmentation techniques

## Future Enhancements
- Predictive analytics integration
- Machine learning models
- Real-time dashboard development
- Advanced customer segmentation
