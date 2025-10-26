# Sample Superstore - Exploratory Data Analysis

## Project Overview
This project performs comprehensive exploratory data analysis (EDA) on the Sample Superstore dataset to uncover insights about sales, profit, and business performance across different dimensions.

**Author:** MD ZIA ARZOO  
**Organization:** The Spark Foundation (Data Science and Business Analytics Intern)  
**Dataset:** [Sample Superstore Dataset](https://bit.ly/3i4rbWl)  
**Tags:** #GRIPAUGUST21 #TSF #DATASCIENCE

## Dataset Information
- **Total Records:** 9,994 transactions
- **Features:** 13 columns
- **Missing Values:** None
- **Geographic Coverage:** United States

### Dataset Columns
- Ship Mode, Segment, Country, City, State, Postal Code
- Region, Category, Sub-Category
- Sales, Quantity, Discount, Profit

## Technologies Used
- Python 3.x
- pandas - Data manipulation
- NumPy - Numerical operations
- Matplotlib - Data visualization
- Seaborn - Statistical visualizations

## Analysis Performed

### 1. Data Quality Assessment
- Checked for missing values (none found)
- Verified data types and structure
- Examined dataset dimensions

### 2. Sales and Profit Analysis
- Analyzed relationship between sales and profit
- Created distribution plots showing profit has direct correlation with sales
- Identified that profit margins vary across regions

### 3. Geographic Analysis

**State-Level Insights:**
- **Highest Deals:** California (2,001), New York (1,128), Texas (985)
- **Lowest Deals:** Wyoming
- **Average Deals per State:** ~204
- **Highest Profit:** Vermont
- **Lowest Profit:** Ohio

**City-Level Insights:**
- **Top Cities:** New York City, Los Angeles, Philadelphia
- **Average Deals per City:** ~19

### 4. Category Analysis
- **Technology:** Highest sales and profit
- **Furniture:** Lowest profit margin
- Analyzed performance across Office Supplies, Technology, and Furniture

### 5. Shipping Mode Analysis
- **Most Common:** Standard Class (5,968 orders)
- **Profit & Discount:** Highest in First Class
- **Sales:** Highest for Same Day shipping

### 6. Correlation Analysis
- **Sales & Profit:** Moderately correlated (positive)
- **Quantity & Profit:** Less moderately correlated
- **Discount & Profit:** Negatively correlated

## Key Findings

1. **Profit-Sales Relationship:** Direct positive correlation exists, but profit margins are inconsistent across regions
2. **Geographic Performance:** California leads in transaction volume; Vermont shows highest profitability
3. **Product Categories:** Technology category drives maximum profit; Furniture needs optimization
4. **Shipping Preferences:** Standard Class dominates volume; First Class yields higher margins
5. **Discount Impact:** Negative correlation with profit suggests need for discount strategy review
6. **Customer Segments:** Home Office segment shows strong performance in both sales and profit

## Visualizations Included
- KDE plots for Sales and Profit distribution
- Pair plots by Category, Region, and Segment
- Correlation heatmap
- Bar charts for state and city-wise analysis
- Pie charts for quantity, category, and shipping mode analysis

## Business Recommendations

1. **Focus on High-Performing States:** Increase marketing efforts in California, New York, and Texas
2. **Optimize Low-Profit Regions:** Investigate and improve operations in Ohio and similar states
3. **Category Strategy:** Expand Technology offerings; review Furniture pricing and costs
4. **Discount Management:** Reevaluate discount policies to improve profit margins
5. **Shipping Optimization:** Promote First Class shipping for better profitability

## How to Run

```python
# Install required libraries
pip install numpy pandas matplotlib seaborn

# Load and run the analysis
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
url = 'https://raw.githubusercontent.com/ziaArzoo/spark-foundation/main/SampleSuperstore%20(1).csv'
df = pd.read_csv(url)

# Run your analysis
```

## Future Work
- Time series analysis for seasonal trends
- Customer segmentation using clustering
- Predictive modeling for sales forecasting
- Product recommendation system
- Regional expansion analysis

## License
This project is part of The Spark Foundation internship program.

## Contact
For questions or collaboration opportunities, please reach out through The Spark Foundation channels.

---
*This analysis demonstrates data exploration techniques and provides actionable business insights for retail operations optimization.*
