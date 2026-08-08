An interactive Sales Analytics Dashboard developed using Microsoft Power BI to analyze sales performance, customer orders, regional performance, product performance, monthly trends, and order status.

This project demonstrates the complete data analytics workflow, from raw data preparation and cleaning to DAX calculations, visualization, and business insight generation.

---

## Project Overview

The objective of this project is to transform raw sales transaction data into an interactive dashboard that provides meaningful insights into business performance.

The dashboard allows users to analyze:

- Overall sales performance
- Number of orders
- Average order value
- Quantity sold
- Regional sales performance
- Product performance
- Monthly sales trends
- Order status distribution

---

## Project Objectives

- Clean and prepare raw sales data
- Handle missing values
- Perform data transformation using Power Query
- Create calculated measures using DAX
- Build meaningful data visualizations
- Analyze sales trends and regional performance
- Generate business insights from the data
- Present findings through an interactive dashboard

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| Microsoft Power BI | Dashboard development and visualization |
| Power Query | Data cleaning and transformation |
| DAX | Calculated measures and business metrics |
| Microsoft Excel | Source dataset |

---

## Dataset

The project uses a sample sales transaction dataset containing:

- Order ID
- Customer Name
- Email
- Region
- Product
- Quantity
- Unit Price
- Order Date
- Delivery Date
- Status
- Payment Method
- Feedback Score

The dataset contains 20 sample sales transactions across multiple regions and products.

---

## Data Cleaning & Transformation

Power Query was used to prepare the dataset before analysis.

The following preprocessing steps were performed:

### Removing Unnecessary Columns

An unnecessary extra column was identified and removed from the dataset.

### Handling Missing Quantity

A missing Quantity value was identified and replaced with a valid value to maintain the transaction record.

### Handling Missing Unit Price

A missing Unit Price value was identified and replaced using the corresponding product price available in the dataset.

### Data Validation

Power Query Column Quality was used to check:

- Valid values
- Empty values
- Errors

### Data Types

Column data types were checked and corrected where required for accurate calculations and visualization.

---

## DAX Measures

The following DAX measures were created for the dashboard.

### Total Sales

```DAX
Total Sales =
SUMX(
    'Sales Data',
    'Sales Data'[Quantity] * 'Sales Data'[Unit Price]
)
```

Calculates total sales by multiplying quantity by unit price for each transaction.

### Total Orders

```DAX
Total Orders =
COUNTROWS('Sales Data')
```

Calculates the total number of sales transactions.

### Total Quantity

```DAX
Total Quantity =
SUM('Sales Data'[Quantity])
```

Calculates the total number of units sold.

### Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders]
)
```

Calculates the average revenue generated per order.

### Delivered Orders

```DAX
Delivered Orders =
CALCULATE(
    [Total Orders],
    'Sales Data'[Status] = "Delivered"
)
```

Calculates the number of delivered orders.

### Cancelled Orders

```DAX
Cancelled Orders =
CALCULATE(
    [Total Orders],
    'Sales Data'[Status] = "Cancelled"
)
```

Calculates the number of cancelled orders.

### Cancellation Rate

```DAX
Cancellation Rate =
DIVIDE(
    [Cancelled Orders],
    [Total Orders],
    0
)
```

Calculates the percentage of orders that were cancelled.

---

## Dashboard KPIs

The dashboard provides the following key performance indicators:

- **Total Sales:** Approximately ₹10.8 lakh
- **Total Orders:** 20
- **Average Order Value:** Approximately ₹54.16K
- **Total Quantity:** 39 units

---

## Dashboard Visualizations

### Sales by Region

A bar chart is used to compare sales performance across different regions and identify high-performing and low-performing regions.

### Monthly Sales Trend

A line chart is used to analyze how sales change over time and identify monthly trends.

### Sales by Product

A column chart is used to compare sales performance across different products.

### Order Status Distribution

A donut chart displays the distribution of:

- Delivered
- Shipped
- Pending
- Cancelled

This provides an overview of order fulfillment performance.

---

## Key Business Insights

Based on the dashboard:

- The business generated approximately **₹10.8 lakh in total sales**.
- The dataset contains **20 orders** and **39 units sold**.
- The average order value is approximately **₹54.16K**.
- **North** has the highest sales among the regions in the dataset.
- The majority of orders are in the **Delivered** status.
- Regional and product-level performance can be compared to identify areas requiring further attention.

---

## Dashboard Preview

![Sales Analytics Dashboard](<img width="1917" height="1022" alt="dashboard" src="https://github.com/user-attachments/assets/9bce1521-96fa-460a-9e0e-84fc5c256b90" />
)
---

## Data Analytics Workflow

```text
Raw Sales Data
       ↓
Power Query
       ↓
Data Cleaning
       ↓
Data Validation
       ↓
DAX Measures
       ↓
Data Visualization
       ↓
Interactive Dashboard
       ↓
Business Insights
```

---

## Project Structure

```text
Sales-Analytics-PowerBI/
│
├── README.md
├── Sales_Analytics_Dashboard.pbix
├── Sales_Data.xlsx
└── dashboard.png
```

### File Description

**README.md**  
Project documentation and analysis details.

**Sales_Analytics_Dashboard.pbix**  
Complete Power BI project containing the data model, DAX measures, and dashboard.

**Sales_Data.xlsx**  
Source dataset used for the project.

**dashboard.png**  
Screenshot of the completed Power BI dashboard.

---

## Skills Demonstrated

- Microsoft Power BI
- Power Query
- DAX
- Data Cleaning
- Data Transformation
- Data Visualization
- Business Intelligence
- Dashboard Development
- KPI Development
- Business Analysis
- Data Interpretation

---

## Future Improvements

The project can be further extended by:

- Adding interactive slicers
- Connecting the dashboard to a live database
- Adding customer segmentation
- Adding profit and cost analysis
- Adding year-over-year sales comparison
- Adding forecasting
- Adding drill-through pages
- Automating data refresh
- Adding more detailed customer analysis

---

## Conclusion

This project demonstrates how Power BI can be used to transform raw sales transaction data into an interactive business intelligence dashboard.

Power Query was used for data preparation and cleaning, DAX was used for analytical calculations, and Power BI visualizations were used to present sales performance, regional trends, product performance, and order fulfillment insights.

The project provides a practical demonstration of using data analytics and business intelligence techniques to support data-driven decision-making.
