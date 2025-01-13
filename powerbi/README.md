# Supermarket Sales Analytics - Power BI Implementation

## Dashboard Overview
This Power BI implementation consists of two main dashboards analyzing supermarket sales data across multiple dimensions.

### Dashboard 1: Sales Performance & Operations Analytics
![Sales Dashboard](/docs/images/Super_Market_Sales_Analytics_Dashboard_1.png)

#### Key Components:
1. KPI Cards
   - Total Revenue
   - Total Products Sold
   - Average Transaction Value
   - Gross Profit Margin

2. Visualizations
   - Daily Sales Trend Analysis
     * Revenue and quantity trends
     * 7-day moving average
   
   - Product Performance Matrix
     * Quantity vs margin analysis
     * Size indicating revenue
   
   - Branch Revenue Analysis
     * Branch-wise distribution
     * Product category breakdown
   
   - Payment Distribution
     * Method-wise split
     * Transaction value patterns

### Dashboard 2: Customer Insights & Product Analytics
![Customer Dashboard](/docs/images/Super_Market_Sales_Analytics_Dashboard_2.png)

#### Key Components:
1. KPI Cards
   - Average Customer Rating
   - Member vs Non-Member Ratio
   - Customer Lifetime Value
   - Product Performance Index

2. Visualizations
   - Customer Segment Analysis
     * Gender distribution
     * Purchase patterns
   
   - Product Category Performance
     * Sales distribution
     * Profitability analysis
   
   - Geographic Performance
     * City-wise analysis
     * Customer density

## Technical Implementation

### Data Model
- Fact Table: Sales Transactions
- Dimensions:
  * Product Categories
  * Customer Types
  * Locations
  * Time Intelligence

### Key DAX Measures
```
// KPI Measures
Total Revenue = 
SUM('supermarket_sales'[Total])

Average Transaction Value = 
DIVIDE(
    SUM('supermarket_sales'[Total]),
    DISTINCTCOUNT('supermarket_sales'[Invoice ID])
)

Member Ratio = 
DIVIDE(
    CALCULATE(
        COUNTROWS('supermarket_sales'),
        'supermarket_sales'[Customer type] = "Member"
    ),
    COUNTROWS('supermarket_sales'),
    0
)
```

## Performance Optimization

### 1. Query Optimization
* Appropriate relationship cardinality
* Efficient data modeling
* Optimized DAX measures

### 2. Visual Optimization  
* Strategic use of bookmarks
* Efficient cross-filtering
* Performance analyzer insights

## Usage Guide

### Navigation

#### 1. Use slicers for:
* Date range selection
* Product category filtering  
* Branch selection

#### 2. Cross-filtering:
* Click on charts to filter related visuals
* Use drill-through for detailed analysis

### Refresh Data

#### 1. Update Data Source:
* Verify connection to supermarket_sales.csv
* Check data types and formats
* Refresh data model

## Maintenance

### Known Issues
* Large data refreshes might take time
* Some cross-filtering needs optimization

### Development Notes
* Power BI Desktop version: Latest
* Required extensions: None
* Development environment: Windows

### Related Documents
* [DAX Documentation](/docs/DAX_Functions_Documentation.pdf)
* [Business Case](/docs/images/Super_Market_Sales_Analysis_By_Venkata_Akhil_Mettu.pptx)
