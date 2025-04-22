# Contoso Sales Data Analysis Portfolio

## Project Overview
A comprehensive analysis of the Contoso retail dataset using PostgreSQL and Python, focusing on various analytical techniques to derive business insights.

## Database Schema
![Contoso Database Schema](Screenshot%202025-04-22%20171824.png)

## Database Details
- **Name**: contoso_100k
- **Type**: PostgreSQL
- **Tables**: 
  - `sales`: Transaction records
  - `product`: Product information
  - `customer`: Customer demographics and details

## Technical Environment

### Database Connection
The project uses JupySQL (formerly IPython-SQL) to interact with PostgreSQL database directly in Jupyter notebooks:

```python
# Import required libraries
import pandas as pd
from sqlalchemy import create_engine
%load_ext sql

# Database connection
%sql postgresql://postgres:legacy@localhost:5432/contoso_100k

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
- Temporal trends in sales
- Year-over-year comparisons
- Seasonal patterns identification

### 3. Cumulative Analysis (`03.cummulative_analysis.ipynb`)
- Running totals of sales
- Moving averages
- Growth trends visualization

### 4. Performance Analysis (`04_Performance_analysis.ipynb`)
- Product performance metrics
- Year-over-year revenue changes
- Sales variance analysis

### 5. Segmentation Analysis (`05_Segmentation_Analysis.ipynb`)
- Product cost segmentation
- Distribution analysis
- Category-based grouping

### 6. Part-to-Whole Analysis (`06_Part_to_whole_Analysis.ipynb`)
- Category sales distribution
- Market share analysis
- Product cost distribution

### 7. Rank Analysis (`07_Rank_analysis.ipynb`)
- Top performing products
- Customer rankings
- Revenue-based hierarchies

### 8. Cohort Analysis (`08_Cohort_analysis.ipynb`)
- Customer cohort analysis
- Retention patterns
- Purchase behavior over time

### 9. Customer Analysis (`09_Customer_report.ipynb`)
- Customer profiling
- Purchase patterns
- Value segmentation

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
